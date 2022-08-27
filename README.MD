# Nucampsite ![Project Image](./imagesREADME/logo.png)  

![Project Image](./imagesREADME/WeekOne.png | width=1400)

> This is a ReadMe template to help save you time and effort.

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


---
## References
[Back To The Top](#table-of-contents)

---

## License

None

---

## Author Info

- Linkedin - [William Knight](https://www.linkedin.com/in/william-knight-357454226/)


[Back To The Top](#table-of-contents)
