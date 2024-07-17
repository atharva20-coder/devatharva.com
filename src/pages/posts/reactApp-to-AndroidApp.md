---
title: React app ➡ Android/iOS app
slug: react-app-to-android-app
date: 2021-7-12
author: Atharva Joshi
read_time: 5
tags: [iconic]
order: 3
hero: https://atharvacodes.netlify.app/static/29483004d9bd7d23af3ebd57ecadf62b/4ef49/ionic.png
draft: false
emoji: "⚛"
---

# Convert your existing Reactjs app to android or iOS app using <img src="https://img.shields.io/badge/Ionic-3880FF?style=for-the-badge&logo=ionic&logoColor=white" style="vertical-align:middle" alt="react-background"> Capacitor

So what exactly is Capacitor? According to documentation

> Capacitor is a cross-platform app runtime that makes it easy to build web apps that run natively on iOS, Android, Electron, and the web. We call these apps “Native Progressive Web Apps” and they represent the next evolution beyond Hybrid apps.

So today we will build our android or ios app using the existing react app.

## Requirments

- Existing <img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" style="vertical-align:middle" alt="react-background"> App
  <br>
- <img src="https://img.shields.io/badge/Ionic-3880FF?style=for-the-badge&logo=ionic&logoColor=white" style="vertical-align:middle" alt="react-background">
  <br>
- <img src="https://img.shields.io/badge/Android-3DDC84?style=for-the-badge&logo=android&logoColor=white" style="vertical-align:middle" alt="react-background"> Studio
  <br>
- <img src="https://img.shields.io/badge/Xcode-007ACC?style=flat-square&logo=Xcode&logoColor=white" style="vertical-align:middle" height="25px" width="100px" alt="react-background">

1. First, go to the root of your existing react app and create a file capacitor.config.json and inside that put the below code.

```
{
  "appId": "io.ionic.nameofyourapp",
  "appName": "nameofyourapp",
  "bundledWebRuntime": false,
  "npmClient": "npm",
  "webDir": "build",
  "cordova": {}
}
```

2.  Now create another file name ionic.config.json and inside that insert the below code.

```
{
  "name": "nameofyourapp",
  "integrations": {
    "capacitor": {}
  },
  "type": "react"
}
```

**Note: replace nameofyourapp in both files with the name of your app.**

3. Now we need to build our react project. To build your react app open your terminal to the root of the project and run the below-mentioned command

```bash
npm run build
```

**_Note: this will create the build folder in your root porject and the name of the folder should match the webDir name inside capacitor.config.json file_**

4. Now we will install ionic globally in our machine. To install ionic globally in your machine open your terminal and run the below command.

```bash
npm install -g @ionic/cli
```

5. Now install the capacitor core in our project.

```bash
npm install @capacitor/core --save
```

## <img src="https://img.shields.io/badge/Android-3DDC84?style=for-the-badge&logo=android&logoColor=white" alt="Android">

6. After that, we will first create an android app with our existing react app. Open your terminal and type

```bash
ionic capacitor add android
```

7. Now run the below command to open your android project in android studio.

```bash
npx cap open android
```

Wait some time and then it will ask you to update the Gradle. Just update the Gradle to the latest version and run the project in the emulator. You can also connect your mobile to run the project live on your mobile phone.
<br><br>
<img src="/src/images/android-mockup.jpeg">

8. Now open the build menu from the android studio and build your apk file.

## <img src="https://img.shields.io/badge/iOS-000000?style=for-the-badge&logo=ios&logoColor=white" alt="iOS">

1. To create ios app run the below command

```bash
ionic capacitor add ios
```

This will install all the required dependencies and ios folder to your project.

2. Now run the below command to open your ios project in Xcode.

```bash
npx cap open ios
```

3. Now open the app in emulator or physical device and build the app.
   Visit the <a href="https://capacitorjs.com/">capacitor homepage</a> for detailed information and documentation.
   Here is the git repository for reference

<br>
Congratulations 🧙 You succesfully converted your React app into <img src="https://img.shields.io/badge/iOS-000000?style=for-the-badge&logo=ios&logoColor=white" style="vertical-align:middle"  alt="iOS"> or <img src="https://img.shields.io/badge/Android-3DDC84?style=for-the-badge&logo=android&logoColor=white" style="vertical-align:middle"  alt="Android">
<br><br><br>
