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

9. Keep in mind flex works so smart! it automatically wraps and adjusts the proportion of layout

10. If you got Transform Error, verify the cache 
> npm cache verify 

or 

> npm cache clean --force

10. bindActionCreators  Is in redux, not in react-redux now.
> import { bindActionCreators } from 'redux';

11. Consider using ... magic (three dots magic a.k.a spread operator)

12. You might read this
> ✅ Your project is ready!

> To run your project, navigate to the directory and run one of the following yarn commands.

> - cd TestSomeNewProject
> - yarn android
> - yarn ios # you need to use macOS to build the iOS project - use managed workflow if you need to do iOS development without a Mac
> - yarn web

12. Those things
>  1. Clear watchman watches: watchman watch-del-all
>  2. Delete node_modules: rm -rf node_modules and run yarn install
>  3. Reset Metro's cache: yarn start --reset-cache
>  4. Remove the cache: rm -rf /tmp/metro-*

13. Visual Studio Code
> F12 Or Ctrl + Left Click  -> Go To Declaration  
> Ctrl + P = Double Shift IntelliJ Alike  
> Alt + Left/Right -> Switch Tab  
> Alt + Up/Down -> Move The Code in a selected Line To Up/Down  
> Ctrl + F12 -> Go To Implementation  
> Ctrl + Shift P -> Command Palette  
> Command Palette + gotoTypeDefinition -> To Type Definition  
> Ctrl + Shfit + O -> Jump To Symbol (Variables / Function)  

14. Restart React-native packager
> $ npx react-native start

15. Put height and width when it comes to showing an image, not only the source

16. Run Metro Bundler on Web
> npx start

17. Lottie And Its Animations
> https://github.com/react-native-community/lottie-react-native  
> https://lottiefiles.com  

18. To Debug, either you can use
> console.log();
or
> Using Browser and go to console.
In emulator, CTRL+M or open developer menu in node (metro bundler)
Likely http://localhost:8081/debugger-ui/ address will appear
Open Inspect Element and go to debugger
> Go to breakpoints and tick pause on exceptions, pause on caught exceptions
> reload the app again
> Do a stepover (F10) 
It will appear the line that makes an error.
