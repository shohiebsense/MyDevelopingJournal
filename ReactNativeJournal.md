1. Delete folders, for example node_modules, quickly
> RMDIR /Q/S foldername
> npm install

2. Error module "Number"
>  close metro bundler and re-run your application.

3. Run App
> npx react-native run-android   

4. Run App without androidx migration
> react-native run-android --no-jetifier       

5.for constants, don't forget to install unimodules first
https://www.npmjs.com/package/expo-constants
https://docs.expo.io/versions/latest/sdk/constants/
> npm install react-native-unimodules    
> Follow the instructions in there
> expo install expo-constants

6. Refresh modules 
> npx react-native eject   
> yarn start --reset-cache
> npx react-native link   

7. Uninstall packages
> npm uninstall --save @unimodules/core

8. Match Parent both width and height
flex: 1,
flexDirection: "row",



