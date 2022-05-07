
# Component Rules


<hr>

- [Comments](#comments)
- [Indents](#indents)
- [Naming Conventions](#naming-conventions)
- [Alignment](#alignment)
- [Spacing](#spacing)
- [Miscellaneous](#miscellaneous)


<a name="comments"></a>
## 1. Comments


* Comment your code. Try to make it as clear as possible.

* Single Line Comment:
    >Use a single line comment for - functions and to explain your code.

    ```javascript
    // Executes On First Render
    componentDidMount(){
      // something
    }
    ```

* Multi Line Comment:
    >Use a multi line comment for Components.

    ```javascript
    /********************************************************************
    Cta Icon

    @param {String} text - Cta text
    @param {Object} icon - Icon
    @param {Boolean} hasBorder - If true, show Bottom Border


    @return Component

    @callback - onPress function will execute on press of cta
    *********************************************************************/
    ```

 <a name="indents"></a>
## 2. Indents

* Use Tabs or spaces for indentation.

* Horizontal indents:
  >Use Tab key for all child Component/View for improved readability.

  ```javascript
  <View style={Styles.testStyle}>
    <View style={Styles.testStyle}>
      <Text>
        Hello World!
      </Text>
    </View>
  </View>
  ```

* Vertical indents:
  >Use empty lines for splitting code into logical blocks.

  ```javascript
  function pow(x, n) {

    let result = 1;
    //              <--
    for (let i = 0; i < n; i++) {
      result *= x;
    }
    //              <--
    return result;

  }
  ```


<a name="naming-conventions"></a>
## 3. Naming Conventions

* Component names should be precise and understandable by everyone.

* Core Components:
    > Name for Core Components should always be generic and precise.

    ```javascript
    // bad
    export const LoginCta = (props) => {

      return(
        <TouchableOpacity onPress={props.onPressCta}>
          <Text>
            {props.loginText}
          </Text>
        </TouchableOpacity>
      );

    }

    // good
    export const BorderCta = (props) => {

      return(
        <TouchableOpacity onPress={props.onPress}>
          <Text>
            {props.text}
          </Text>
        </TouchableOpacity>
      );

    }
    ```

* App/Complex Components:
    > Name for App/Complex Components can be module/screen specific. (If they're not being used in any other module/screen).
    If any such Component is used in more than 1 module/screen, it's name can be generic.

    ```javascript
    // CampaignDetails component will be used only in Campaign Module.
    export class CampaignDetails extends Component{

    }
    ```

* Props:
    > For Core Components, props should be generic and precise. Also, it's better to not change name of built-in props.

    ```javascript
    // bad
    export const LinkCta = (props) => {

      return(
        <TouchableOpacity onPress={props.onPressLinkCta}>
          <Text>
            {props.linkCtaText}
          </Text>
        </TouchableOpacity>
      );

    }

    // good
    export const LinkCta = (props) => {

      return(
        <TouchableOpacity onPress={props.onPress}>
          <Text>
            {props.text}
          </Text>
        </TouchableOpacity>
      );

    }
    ```

    <br />

    > For App/Complex Components, prop name depends on module. In this case, prop name will be it's purpose in that component.
    For ex: Here prop `storeName` will always be used for Store name.

    ```javascript
    export const StoreCard = (props) => {

      return(
        <TouchableOpacity
          activeOpacity={0.8}
          style={component_styles.storeCardContainer()}
          onPress={props.onPress}
        >
          <View style={component_styles.storeCardInnerContainer()}>
            <View>
              <View>
                <CustomText h2>{props.storeName}</CustomText>
              </View>

              <View style={component_styles.storeCardAddress()}>
                <CustomText p>{props.address}</CustomText>
              </View>
            </View>

            <CustomText small>{props.status}</CustomText>
          </View>
        </TouchableOpacity>
      );

    }
    ```

    <br />

    > Always use camelCase for prop names

    ```javascript
    // bad
    <OrderInformation
      CustomerName="Rahul"
      phone_number="12345678"
    />

    // good
    <OrderInformation
      customerName="Rahul"
      phoneNumber="12345678"
    />
    ```


* Style:
    > Style name should always be in camelCase.

    > You can also make Styles which are used more often.

    ```javascript
    mR8:{
      marginRight: 8
    }

    flexRow:{
      flexDirection: 'row'
    }
    ```

* Icon:
    > Icon name should always be in camelCase.

<a name="alignment"></a>
## 4. Alignment

  ```javascript
  // bad
  <Cta heading="text"
       subHeading="text" />

  // good
  <Cta
    heading="text"
    subHeading="text"
  />

  // if props fit in one line then keep it on the same line
  <Cta heading="text" />

  // children get indented normally
  <Cta
    heading="text"
    subHeading="text"
  >
    <Text>Hello World!</Text>
  </Cta>
  ```

<a name="spacing"></a>
## 5. Spacing

* Always include a single space in your self-closing tag.

  ```javascript
  // bad
  <Cta/>

  // very bad
  <Cta                 />

  // bad
  <Cta
   />

  // good
  <Cta />
  ```

<a name="miscellaneous"></a>
## 6. Miscellaneous

* Use Spread operator to pass props to a React component.

  ```javascript
  export const CustomTextInput = (props) => {

    return(
      <TextInput {...props} />
    );

  }
  ```

---
Sources:

[Airbnb React/JSX Style Guide](https://airbnb.io/javascript/react/),
[Javascript/Coding Style](https://javascript.info/coding-style)
