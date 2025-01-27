# ModdakirSDK-Android
Android Library connects you Directly with teacher to learn the Holy Qur’an  📖

##  Getting Started
These instructions will help you setup, integrate and run your project integrated with our SDK.


##  Integration Steps
1. Copy the AAR file
Place the .aar file in the libs directory of your Android module (e.g., app/libs).
If the libs folder doesn't exist, create it manually in your module's directory.

2. Update the build.gradle File
Open the build.gradle file of your module (e.g., app/build.gradle).

Add the following block to include the libs folder as a repository:
```java
repositories {
    flatDir {
        dirs 'libs'
    }
}
```
Add the AAR file as a dependency:
```java
dependencies {
    implementation(name: 'moddakir-sdk-v1.x.x', ext: 'aar')
}
```
3. Sync the Project
Click on Sync Now in Android Studio to apply the changes.

4. Check the Dependencies
Open the Project Structure (File > Project Structure > Dependencies).
Verify that your AAR file has been added to the dependencies list.

5. Handle Transitive Dependencies
3- Add In your build.gradle these dependencies :
```java
dependencies {
    implementation(name: 'moddakir-sdk-v1.0', ext: 'aar')
}
```

2. Add the dependency
```java
 dependencies {

     // Add moddakir-sdk.aar path
    implementation(files("libs/moddakir-sdk.aar"))

    // Circle Imageview
    implementation("de.hdodenhof:circleimageview:3.0.1")

    // Localization
    implementation("com.akexorcist:localization:1.2.11")

    // Agora
    implementation("io.agora.rtc:full-sdk:4.3.2")
    implementation("io.agora.rtm:rtm-sdk:2.1.12")

    // RxJava
    implementation("io.reactivex.rxjava2:rxandroid:2.1.1")
    implementation("io.reactivex.rxjava2:rxjava:2.2.17")

    // Retrofit
    implementation("com.squareup.retrofit2:converter-gson:2.8.1")
    implementation("com.squareup.retrofit2:adapter-rxjava2:2.3.0")

    // Easy Permissions
    implementation("pub.devrel:easypermissions:3.0.0")

    // Timber
    implementation("com.jakewharton.timber:timber:4.7.1")
}
```



##  Quick Start

Call makeCall method :
```java
makeCall(String moddakirId,String moddakirKey, Context Context ,String Gender,
String Name,String Phone,String Email,
String Language, boolean isLightMode, Integer primaryColor)
```

### to initialize a new call with a random teacher and it will be responsible for:

Validate the user’s name,user's phone number,user's email ,user's gender and language.

Present the waiting screen to the user while trying to connect with a teacher.

Present the in-call screen once the teacher accepts the call.

Present the rating screen after the call ends if it continues more than 30 seconds.

Present the rating done pop-up after rating the teacher and the call.


### this funtion take:

moddakirId : Contact Moddakir Support to get this value

moddakirKey: Contact Moddakir Support to get this value

Context: Context of activity that will start the call

Gender: The user’s gender "male/female"

Name: The user's Name

Phone: The user Phone include the country code

Email: The user Email

Language: application language "ar/en/fr/in/ur"

isLightMode: 'true' if the app is light theme / 'false' if app is dark theme

primaryColor: apply your primary color
