# UniRidePrerelease
Prerelease for UniRide app 
# Instructions for building apk for your reactive native project 
instructions for building an apk file for react native project can be found in the following links 
https://android.jlelse.eu/preparing-a-reach-native-android-app-for-production-f063413d5633
https://facebook.github.io/react-native/docs/signed-apk-android.html

EVen though the documnent is self explanatory there are some issues while building an apk in a windows machine. Some of the major errors faced while creating apk in a windows machine and their remedys are explained below for future reference. 
# Apk for windows
# Setting up gradle variables

No gradle.properties file found under the given location.SO use the gradle.properties file under your project directory. the path  will be 
your-project-directory/android/gradle.properties.
 # Adding signing config to your app's gradle config 
 Edit android/app/build.gradle 
 Make sure that the file names and alias names specified under this section matches to the one you have added in gradle.properties file.
 Do not forget  to add the code in 
 buildTypes { 
 release {
            ...
            signingConfig signingConfigs.release    // ## DO not forget this line of code 
        }
    }
 
 # Generating the release APK
 
cd android && ./gradlew assembleRelease  
 windows doesnt recognise this command . So we have to go the android directory and then run ./gradlew assembleRelease command seperately. 

$ cd android 
$ ./gradlew assembleRelease 


