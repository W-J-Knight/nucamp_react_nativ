# Nucampsite ![Project Image](./assets/images/logo.png)  

<!-- ![Project Image](assets/images/WeekOne.png | width=1400) -->
<img src="assets/images/WeekOne.png " width="100">

<!-- > This is a ReadMe template to help save you time and effort. -->

---

### Table of Contents
You're sections headers will be used to reference location of destination.

- [Description](#description)
- [Technologies](#technologies)
<!-- - [How To Use Week One](#how-to-use-week-one) -->
- [References](#references)
- [License](#license)
- [Author Info](#author-info)
- [Week one](#week-one)

---

## Description

This is classwork from an awesome online bootcamp called Nucamp. I attending Full Stack Web + Mobile Development this product from React Native section.This section is a four week course.

## Technologies

- node v16.13.2
- expo-cli 
- VS Code
- Android Studio
- git is optional
- jdk (java)

[Back To The Top](#table-of-contents)

---

<!-- ## How To Use
Once download and install. In the terminal type expo start. -->
#### Installation
Could just download the zip file off the github repository.Or use git.

```git
git clone https://github.com/W-J-Knight/nucamp_react_native
```


[Back To The Top](#table-of-contents)

---

## Week One
### Installing Andriod studio
This for Ubuntu users.You can follow my instructions or go to the https://linuxhint.com//install-android-studio-ubuntu22-04/ where I learn how in the terminal.
1. Install jdk (java)
```bash
sudo apt install openjdk-11-jdk
```
2.  Check to see if installation was successfully.
```bash
java --version
```
3. Adding a PPA for andriod studio
```bash
$ sudo add-apt-repository ppa:maarten-fonville/android-studio
```
4. Update the Ubuntu system to use the new PPA.
```bash
sudo apt update
```
5. Now time to install andriod studio.
```bash
sudo apt install android-studio -y
```
### Installing VS Code
You could install from the  Ubuntu Software GUI. Or download it vs code the debian version. Then in the download folder open up a termainal. Type in sudo apt install ./code_*
```bash
sudo apt install ./code_*
```
### Installing NVM and node
1. First installing nvm for node. Download the script for installing nvm. Use  the curl \command.
 If  you not have curl. You install it in the terminal.
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install curl
curl --version
```
\
2. downloading the script and installing nvm using the script.
```bash
curl -sL https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.0/install.sh -o install_nvm.sh | bash 
```
\
3. Update the bashrc .
```bash 
source ~/.bashrc
```
#### Install Node v16.13.2 useing Nvm

```bash
nvm install v16.13.2
```
```bash
nvm alias default 16.13.2
```
### Installing git
1. Add repository
```bash
sudo add-apt-repository ppa:git-core/ppa
sudo apt update
sudo apt install git
```
2. Update your system to the PPA
```bash
sudo apt update
```
3. Install git from PPA

```bash
sudo apt install git
```
### Install the Expo CLI tool globally with npm
1. Installing expo-cli
```bash
sudo npm install -g expo-cli
```
2. To confirm your installation of expo-cli.

```bash
expo-cli
```
---
## Course Setup
###  Exercise: Generate and serve a React Native project using expo init
1. If you in nucamp bootcamp open terminal your 4-React-Native directory.
Run the command expo init nucampsite -t blank --npm. The -t stand for a blank template. The --npm stand for this project uses npm.
```bash
expo init nucampsite -t blank --npm
```
2. Move in your project.
```bash
cd nucampsite
```
3. Start the server. Default port exp://192.168.1.12:19000.
```bash
expo start
```
4. Stop server **ctl + c**
---
## Exercise: Update to Locked Versions
1. For project the bootcamp use expo 44. To sure you are useing the same version. Run the command below in the nucampsite directory.
```bash
npm install expo@44
```

3. The same go for react, react-dom, and react-native. 
```bash
expo install react@17.0.1 react-dom@17.0.1 react-native@0.64.3
```

4. Make sure you have the right versions. Open directory in VS Code.Look at the  package.json file.



5. On Android studio. Go to [developer android ](https://docs.expo.dev/workflow/android-studio-emulator/) to .In the bootcamp use pixal 5 device.Have the device run. Start the script.

6. Change the text in App.js. From 'Open App.js to working on your app!' to Hello World!!! In the default function App()
---
```jsx

export default function App() {
  return (
    <View style={styles.container}>
      <Text>Open up App.js to start working on your app!</Text>
      <StatusBar style="auto" />
    </View>
  );
}
```
```jsx

export default function App() {
  return (
    <View style={styles.container}>
      <Text>Hello World!!!</Text>
      <StatusBar style="auto" />
    </View>
  );
}
```
---
 ## Exercise: React Native Components Part 1
In class we add the campsites.js to the shared folder. 
Then add image folder to asset folder.
### Install React Native Elements
Use expo to install packages. Use the command below.
```bash
expo install react-native-elements@3.4.2 react-native-safe-area-context@3.3.2
```
### Create MainComponent.js
Make MainComponent.js inside screen folder
1. Imports in MainComponent.js
```jsx
import { useState } from 'react';
import { CAMPSITES } from '../shared/campsites';
import DirectoryScreen from "./DirectoryScreen";
```
2. Create a arrow in the MainComponent.js call Main and export Main as default.
Use useState to setup campsites array. 
3. Return a shelf tag DirectoryScreen this prop of campsites equal to campsites array.
```jsx
const Main = () => {
  const [campsites, setCampsites] = useState(CAMPSITES);

    return <DirectoryScreen campsites={campsites} />;

};

export default Main;

```
### Create DirectoryScreen.js
1. Make DirectoryScreen.js in the screens folder.
2. Import Avatar and ListItem from 'react-native-elements'.
```jsx
import { FlatList } from 'react-native';
import { Avatar, ListItem } from 'react-native-elements';

```
3. Create arrow function call DirectoryScreen export the function. Pass props as argument.
4. Inside DirectoryScreen arrow.Create arrow function call renderDirectoryItem.
5. Coping from Direction from nucamp\
Inside the opening and closing tag of the ListItem create a self-closing tag with the Avatar component passing it two props source and rounded setting source equal to campsite.image and leaving rounded equal to nothing. (We can set the rounded prop equal to nothing leaving out the equal sign because it is a boolean value which is shorthand for setting it equal to true).
After the Avatar component but still between the opening and closing tags of ListItem add a component named ListItem.Content using an opening and closing tag.
Between the ListItem.Content opening and closing tag create an opening and closing tag of ListItem.Title passing campsite.name between the opening and closing tags in curly brackets.
Still inside the ListItem.Content opening and closing tag create another opening and closing tag of ListItem.Subtitle passing campsite.description between the opening and closing tags in curly brackets.
```jsx
const DirectoryScreen = (props) => {
    const renderDirectoryItem = ({ item: campsite }) => {
        return (
            <ListItem>
                <Avatar source={campsite.image} rounded />
                <ListItem.Content>
                    <ListItem.Title>{campsite.name}</ListItem.Title>
                    <ListItem.Subtitle>
                        {campsite.description}
                    </ListItem.Subtitle>
                </ListItem.Content>
            </ListItem>
        );
    }

  return (
    <FlatList 
        data={props.campsites}
        renderItem={renderDirectoryItem}
        keyExtractor={(item) => item.id.toString()}
    />
  )
}

export default DirectoryScreen
```
## Update App.js
Coping from Direction from nucamp
1. Deleted old imports and replaced with a single import for Main from './screens/MainComponent'.
2. Deleted the style sheet at the bottom of the file.
3. Replaced everything in the return statement with a single tag of <Main/>.
```jsx
import Main from './screens/MainComponent';

export default function App() {
    return <Main />;
}
```
---
 ## Exercise: React Native Components Part 2
Coping from Direction from nucamp
### Set Up New Folders
1. Create a new folder named features/ just inside the nucampsite/ folder.
2. Create another new folder inside the features/ folder that you just created named campsites/. 
3. You should now have two new folders, features/ with another new folder named campsites/ inside of that.
### Create CampsiteInfoScreen.js
1. Add a file named CampsiteInfoScreen.js in the screens/ folder.
2. Import RenderCampsite from '../features/campsites/RenderCampsite'. This component will be created in a following step.
3. Set up the function component as an arrow function set equal to a const named CampsiteInfoScreen, passing one parameter of props to the arrow function.
4. Export the CampsiteInfoScreen as the default export at the bottom of the file.
5. To the CampsiteInfoScreen component, a return statement returning a single self-closing tag of RenderCampsite, passing it a single prop of campsite equal to props.campsite.
```jsx 
import RenderCampsite from '../features/campsites/RenderCampsite'

const CampsiteInfoScreen = (props) => {

    return <RenderCampsite campsite={props.campsite} />;

}

export default CampsiteInfoScreen
```
### Create RenderCampsite.js
Coping from Direction from nucamp
1. Create a new file named RenderCampsite.js inside the features/campsites/ folder created earlier.
2. Import the Text and View components from 'react-native'.
3. Import the Card component from from 'react-native-elements'.
4. Set up a function component named RenderCampsite, and destructure a property named campsite in the function's parameter list.
5. Export the RenderCampsite as the default at the bottom of the file.
6. Set up an if statement to check if campsite is a truthy value. This can be done by simply passing campsite inside the parenthesis of the if statement.
7. Inside the if block, return the Card component imported from react-native-elements, passing it the prop containerStyle equal to padding: 0.
8. Between the Card component's opening and closing tags, add a Card.Image tag with a prop of source equal to campsite.image.
9. Between the Card.Image component's opening and closing tags, add a View component with a style prop, setting the following style properties:
    * justifyContent: 'center'
    * flex: 1
10. Between the View component's opening and closing tags, add a Text component with a style prop, setting the following style properties:

    * color: 'white'
    * textAlign: 'center'
    * fontSize: 20
11. Between the Text component's opening and closing tags, display the campsite name by using campsite.name inside curly brackets:
12. Below the Card.Image closing tag but still within the Card tag, add another Text component with a style prop, setting a style prop of margin: 20.
13. Between the opening and closing tags, display the campsite description within this Text component, using campsite.description inside curly braces:
14. Outside of the if statement, handle the case for when campsite is false and the code inside the if block is not returned. To do this, return an empty View component below and outside of the if statement.
15. RenderCampsite.js should like the as below.

```jsx
import { Text, View } from "react-native";
import { Card } from "react-native-elements";

const RenderCampsite = ({ campsite }) => {
     if(campsite){return (
        <Card containerStyle={{ padding: 0 }}>
            <Card.Image source={campsite.image}>
                <View style={{ justifyContent: "center", flex: 1 }}>
                    <Text
                        style={{
                            color: "white",
                            textAlign: "center",
                            fontSize: 20,
                        }}
                    >
                        {campsite.name}
                    </Text>
                </View>
            </Card.Image>
        </Card>
    );
};return <View />;
}
export default RenderCampsite;
```
###  Update DirectoryScreen.js 
Coping direction from Nucamp
1. Then update DirectoryScreen.js as follows:
2. Add an onPress prop to the ListItem component returned from the renderDirectoryItem function used by the FlatList.
3. Set the onPress prop to an arrow function, and call the custom callback function props.onPress, passing it an argument of campsite.id.
```jsx
<ListItem onPress={() => props.onPress(campsite.id)}>
```
---
## Exercise: Navigation Part 1
### Install React Navigation and its dependencies
Coping directions fron Nucamp
1. With your terminal open to your project folder, install React Navigation and its dependencies into your project with the following two commands:
```bash 
expo install @react-navigation/native@5.9.8 @react-navigation/stack@5.14.9 react-native-gesture-handler
expo install react-native-screens react-native-safe-area-context @react-native-community/masked-view
```
2. We will also need to install a library called expo-constants:

```bash 
expo install expo-constants
```

3. A specific version of the library react-native-reanimated is required for use with this course. Install that now using the following yarn command:
```bash 
expo install expo-constants
```
npm install react-native-reanimated@2.2.0

### Update App.js

1. Open App.js and make the following updates:
2. Import the NavigationContainer component from '@react-navigation/native'.
3. In the return statement, create an opening and closing NavigationContainer tag that wraps around the Main tag.
```jsx
import Main from './screens/MainComponent';
import { NavigationContainer } from '@react-navigation/native';

export default function App() {
    return (
        <NavigationContainer>
            <Main />
        </NavigationContainer>
    );
}
```
### Update MainComponent.js

1. Open MainComponent.js and update it as follows:
2. Remove the useState import from 'react'.
3. Remove the CAMPSITES import from '../shared/campsites'.
4. Import Platform from 'react-native'.
5. Import Constants from 'expo-constants'.
6. Import createStackNavigator from '@react-navigation/stack'.
7. Create a function component named DirectoryNavigator above the Main function component.
8. Inside the function body of DirectoryNavigator, create a constant named Stack set equal to a call to createStackNavigator(), passing in no arguments.
9. Set up a return statement for the DirectoryNavigator component, returning a Stack.Navigator as the top level component, using an opening and closing tag.
10. Inside the Stack.Navigator opening tag, pass in a prop called initialRouteName, set equal to the string 'Directory'.
11. Still inside the Stack.Navigator opening and closing tags, pass in another prop called screenOptions, set equal to the following object (remember to wrap this object in a second set of curly brackets):
13. Inside the opening and closing Stack.Navigator tag, create a self-closing Stack.Screen tag and give it the following props:
    *name equal to the string 'Directory'.
    *component equal to the DirectoryScreen component.
    *options equal to the object:
14. Create another self-closing Stack.Screen tag inside the Stack.Navigator tag, and give it the following props:
    *name equal to the string 'CampsiteInfo'.
    *component equal to the CampsiteInfoScreen component.
    *options equal to the following arrow function:
```jsx
({ route }) => ({
    title: route.params.campsite.name
})
```
15. Inside the Main component, remove the two const declarations making use of the useState() hook. 
16. Inside the return of Main, add another style property of paddingTop, equal to the following ternary operator expression:
```jsx
Platform.OS === 'ios' ? 0 : Constants.statusBarHeight
```
17. Remove the DirectoryScreen and CampsiteInfoScreen tags that are being returned from Main.
18. Between the opening and closing View tag where we just removed the DirectoryScreen and CampsiteInfoScreen tags, create a self-closing DirectoryNavigator tag.
```jsx
import { Platform, View } from 'react-native';
import Constants from 'expo-constants';
import CampsiteInfoScreen from './CampsiteInfoScreen';
import DirectoryScreen from './DirectoryScreen';
import { createStackNavigator } from '@react-navigation/stack';

const DirectoryNavigator = () => {
    const Stack = createStackNavigator();
    return (
        <Stack.Navigator
            initialRouteName='Directory'
            screenOptions={{
                headerStyle: {
                    backgroundColor: '#5637DD'
                },
                headerTintColor: '#fff'
            }}
        >
            <Stack.Screen
                name='Directory'
                component={DirectoryScreen}
                options={{ title: 'Campsite Directory' }}
            />
            <Stack.Screen
                name='CampsiteInfo'
                component={CampsiteInfoScreen}
                options={({ route }) => ({
                    title: route.params.campsite.name
                })}
            />
        </Stack.Navigator>
    );
};

const Main = () => {
    return (
        <View
            style={{
                flex: 1,
                paddingTop:
                    Platform.OS === 'ios' ? 0 : Constants.statusBarHeight
            }}
        >
            <DirectoryNavigator />
        </View>
    );
};

export default Main;
```
## Update DirectoryScreen.js

1. Open DirectoryScreen.js and update it as follows:
2. Import the useState hook from 'react'.
3. Import the CAMPSITES array from '../shared/campsites'.
4. On the first line of the DirectoryScreen function body, create a state variable called campsites and a setting function called setCampsites, using the useState hook passing the CAMPSITES array as the initial value for the state variable. 
5. Set the data prop of the FlatList component to the state variable campsites.
6. Destructure a prop value of navigation in the parameter list of DirectoryScreen function, replacing the previous value of props.
7. In the onPress prop of the ListItem component, change the arrow function to the following code:
```jsx 
() => navigation.navigate('CampsiteInfo', {campsite})
```
```jsx 
import { useState } from 'react';
import { FlatList } from 'react-native';
import { Avatar, ListItem } from 'react-native-elements';
import { CAMPSITES } from '../shared/campsites';

const DirectoryScreen = ({ navigation }) => {
    const [campsites, setCampsites] = useState(CAMPSITES);

    const renderDirectoryItem = ({ item: campsite }) => {
        return (
            <ListItem
                onPress={() =>
                    navigation.navigate('CampsiteInfo', { campsite })
                }
            >
                <Avatar source={campsite.image} rounded />
                <ListItem.Content>
                    <ListItem.Title>{campsite.name}</ListItem.Title>
                    <ListItem.Subtitle>
                        {campsite.description}
                    </ListItem.Subtitle>
                </ListItem.Content>
            </ListItem>
        );
    };
    return (
        <FlatList
            data={campsites}
            renderItem={renderDirectoryItem}
            keyExtractor={(item) => item.id.toString()}
        />
    );
};

export default DirectoryScreen;
```
 Update CampsiteInfoScreen.js

1. Then, open CampsiteInfoScreen.js and update it as follows:
2. Destructure the route prop in the parameter list of the CampsiteInfoScreen function, replacing the previous value of props.
3. On the first line of the CampsiteInfoScreen function body, use destructuring again to create a campsite variable from the route.params object.
4. Pass the campsites variable in as the value of the campsites prop for the RenderCampsite component.
```jsx
import RenderCampsite from '../features/campsites/RenderCampsite';

const CampsiteInfoScreen = ({ route }) => {
    const { campsite } = route.params;
    return <RenderCampsite campsite={campsite} />;
};

export default CampsiteInfoScreen;
```
---
## Week 1 Workshop Assignment
### Task 1
Coping direction for Nucamp

1. Create two new files in the screens/ folder: AboutScreen.js and ContactScreen.js.
2. Inside these files, set up the AboutScreen and ContactScreen components as function components, and have them both return an empty ScrollView component, with both the opening and closing tags like this: <ScrollView> </ScrollView> (you will be adding content inside the ScrollView in Task 2). Include the necessary imports and set up both components as the default export. 
3. Next, update MainComponent. Import the AboutScreen and ContactScreen components.
4. You need to create a Stack Navigator for both the AboutScreen and ContactScreen components. Use the Stack Navigator for the HomeScreen (HomeNavigator) as your guide. 
5.For the AboutScreen Stack Navigator give the Stack.Screen a name of 'About' (the options prop here can be omitted since the title will by default be set to whatever the name prop is set to).
6. For the ContactScreen Stack Navigator give the Stack.Screen a name of 'Contact' and in the options give it a title of 'Contact Us'.
7. Then add Drawer.Screen tags inside the Drawer.Navigator opening and closing tags below the tags that are already being used for the Home and Directory screens (the order of these tags determine the order displayed in the drawer).
8. In the Drawer.Screen tag for the AboutNavigator set the name to 'About' (this screen doesn't require an options prop since the title will default to the value of the name prop) and set the component to AboutNavigator.
9. In the Drawer.Screen tag for the ContactNavigator set the name to 'Contact' and in the options give it a title of 'Contact Us'. Also, set the component to ContactNavigator.
10. At the end of this task, you should be able to swipe right on your emulator to bring up the drawer navigator and see the About and Contact Us links there. When you follow them, you will be taken to a blank page, with just the screen title at the top.
### Task 2
Coping direction from NuCamp
In this task, you will update the ContactScreen component to show the address of the company HQ as shown in the instruction video as well as the screenshot below. You will only need to update the ContactScreen.js file.

Address information:
1. You should display the address, phone, and email as shown in the screenshot below:
    * 1 Nucamp Way
    * Seattle, WA 98001
    * U.S.A.

    * Phone: 1-206-555-1234
    * Email: campsites@nucamp.co   

2.  Use a Card component from react-native-elements (RNE) to design this page. Place the Card inside the ScrollView component you created in Task 1. 
3. Set the wrapperStyle prop on the Card to give it an inner margin of 10, using the object format: 

    * wrapperStyle={{margin: 20}}
4. Use the Card.Title component inside the opening and closing tag of the Card to set the title to Contact Information (this component works similar to the Text tag where you can put plain text inside the opening and closing tags).
5. Add a Card.Divider self-closing tag after the Card.Title.

6. Use multiple Text components from React Native for the address, phone number, and email lines. To add space between the address and the phone number, add a style prop with the value of marginBottom: 10 to the final Text component. (The one that displays "U.S.A")

## Task 3  
Copy direction from Nucamp

In this task, you will update the AboutScreen component to show the Mission and Community Partners of the company. You will only need to update the AboutScreen.js file.

1. Use the Card, Card.Title, Card.Divider, and Text components in the Mission component.


2. On the Card component do not apply a wrapperStyle prop and on the Text component give it a style prop with margin: 10.

3. The mission statement should be preceded by a title of "Our Mission". You can use the Card.Title component for this, with a Card.Divider after the title.

4. Text for the mission statement:
```
We present a curated database of the best campsites in the vast woods and backcountry of the World Wide Web Wilderness. We increase access to adventure for the public while promoting safe and respectful use of resources. The expert wilderness trekkers on our staff personally verify each campsite to make sure that they are up to our standards. We also present a platform for campers to share reviews on campsites they have visited with each other.
```
7. The community partnership information is obtained from the partners.js file in the shared folder by the AboutScreen component, so you will need to import it. Set up a state variable inside the function body of AboutScreen and initialize 

8. Go to the empty ScrollView component that you set up in Task 1 in the AboutScreen function's return statement. Inside the ScrollView, render the Mission component you set up earlier. 

9. After the rendering of the Mission component, render a Card component with the title "Community Partners". Again, you can use a Card.Title component for this with a Card.Divider after the title).

10. Then, inside the Card use the map method on the partners data passing partner as a parameter to the map method's function. (Remember when using map in JSX you must put everything inside curly brackets)

11. Then the map's function should return a ListItem component. Make sure to set a key prop on the ListItem using the partner.id value. (Unlike the Directory component, this ListItem will not need a onPress prop nor the navigate function as, unlike the items in the Directory screen, the items in this list will not be links.)

12.  Use an Avatar component in the ListItem with the prop rounded and source setting the source prop to partner.image

13. Use a ListItem.Content component below the Avatar tag nesting a ListItem.Title and ListItem.Subtitle between the opening and closing tags and using the partner.name for the ListItem.Title and the partner.description for the ListItem.Subtitle.

Turn in page
About
```jsx
import { useState } from "react";
import { Text, ScrollView } from "react-native";
import { Card } from "react-native-elements";
import { PARTNERS } from "../shared/partners";
import { Avatar, ListItem } from 'react-native-elements';

const Mission = () => {
    return (
        <Card >
            <Card.Title>Our Mission</Card.Title>
            <Card.Divider />
            <Text style={{ margin: 10 }}>
                We present a curated database of the best campsites in the vast
                woods and backcountry of the World Wide Web Wilderness. We
                increase access to adventure for the public while promoting safe
                and respectful use of resources. The expert wilderness trekkers
                on our staff personally verify each campsite to make sure that
                they are up to our standards. We also present a platform for
                campers to share reviews on campsites they have visited with
                each other.
            </Text>
        </Card>
    );
};

const AboutScreen = () => {
    const [partners, setPartners] = useState(PARTNERS);

    return (
        <ScrollView>
            <Mission />
            <Card>
                <Card.Title>Community Partners</Card.Title>
                <Card.Divider />
                {partners.map((partner) => {
                    return(
                        <ListItem key={partner.id}>
                            <Avatar source={partner.image} rounded />
                            <ListItem.Content>
                                <ListItem.Title>{partner.name}</ListItem.Title>
                                <ListItem.Subtitle>
                                    {partner.description}
                                </ListItem.Subtitle>
                            </ListItem.Content>
                        </ListItem>
                    );
                })}
            </Card>
        </ScrollView>
    );
};

export default AboutScreen;
```
CotactScreen.js
```jsx
import { Text, ScrollView } from "react-native";
import { Card } from "react-native-elements";


const ContactScreen = () => {
    return (
        <ScrollView>
            <Card wrapperStyle={{ margin: 10 }}>
                <Card.Title>Contact Information</Card.Title>
                <Card.Divider />
                <Text>1 Nucamp Way</Text>
                <Text>Seattle, WA 98001</Text>
                <Text style={{marginBottom: 10 }}>U.S.A</Text>
                <Text>Phone: 1-206-555-1234</Text>
                <Text>Email: campsites@nucamp.co</Text>
            </Card>
        </ScrollView>
    );
};

export default ContactScreen;
```
MainCompontent

```jsx
import { Platform, View } from "react-native";
import Constants from "expo-constants";
import CampsiteInfoScreen from "./CampsiteInfoScreen";
import DirectoryScreen from "./DirectoryScreen";
import { createStackNavigator } from "@react-navigation/stack";
import { createDrawerNavigator } from "@react-navigation/drawer";
import HomeScreen from "./HomeScreen";
import AboutScreen from "./AboutScreen";
import ContactScreen from "./ContactScreen";

const Drawer = createDrawerNavigator();

const screenOptions = {
    headerTintColor: "#fff",
    headerStyle: { backgroundColor: "#5637DD" },
};

const HomeNavigator = () => {
    const Stack = createStackNavigator();
    return (
        <Stack.Navigator screenOptions={screenOptions}>
            <Stack.Screen
                name="Home"
                component={HomeScreen}
                options={{ title: "Home" }}
            />
        </Stack.Navigator>
    );
};

const DirectoryNavigator = () => {
    const Stack = createStackNavigator();
    return (
        <Stack.Navigator
            initialRouteName="Directory"
            screenOptions={screenOptions}
        >
            <Stack.Screen
                name="Directory"
                component={DirectoryScreen}
                options={{ title: "Campsite Directory" }}
            />
            <Stack.Screen
                name="CampsiteInfo"
                component={CampsiteInfoScreen}
                options={({ route }) => ({
                    title: route.params.campsite.name,
                })}
            />
        </Stack.Navigator>
    );
};

const AboutNavigator = () => {
    const Stack = createStackNavigator();
    return (
        <Stack.Navigator screenOptions={screenOptions}>
            <Stack.Screen
                name="About"
                component={AboutScreen}
                // options={{ title: "About" }}
            />
        </Stack.Navigator>
    );
};

const ContactNavigator = () => {
    const Stack = createStackNavigator();
    return (
        <Stack.Navigator screenOptions={screenOptions}>
            <Stack.Screen
                name="Contact"
                component={ContactScreen}
                options={{ title: "Contact Us" }}
            />
        </Stack.Navigator>
    );
};

const Main = () => {
    return (
        <View
            style={{
                flex: 1,
                paddingTop:
                    Platform.OS === "ios" ? 0 : Constants.statusBarHeight,
            }}
        >
            <Drawer.Navigator
                initialRouteName="Home"
                drawerStyle={{ backgroundColor: "#CEC8FF" }}
            >
                <Drawer.Screen
                    name="Home"
                    component={HomeNavigator}
                    options={{ title: "Home" }}
                />
                <Drawer.Screen
                    name="Directory"
                    component={DirectoryNavigator}
                    options={{ title: "Directory" }}
                />
                <Drawer.Screen
                    name="About"
                    component={AboutNavigator}
                    // options={{ title: "About"}}
                />
                <Drawer.Screen
                    name="Contact"
                    component={ContactNavigator}
                    options={{ title: "Contact Us" }}
                />
            </Drawer.Navigator>
        </View>
    );
};

export default Main;
```

---
## Icons and More
##  Exercise: Icons, Favorites, and Comments
1. This exercise the take to learn about useState.
the git commit is  "Icons, Favorites, and Comments"








---

## References
[Back To The Top](#table-of-contents)

---

## License

Copyright (c) [2022] [William Knight]

MIT License

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

---

## Author Info

- Linkedin - [William Knight](https://www.linkedin.com/in/william-knight-357454226/)


[Back To The Top](#table-of-contents)
