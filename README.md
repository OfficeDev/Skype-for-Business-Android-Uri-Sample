# Skype for Business Mobile URI SDK Sample

**Table of contents**

* [Device requirement](#device-requirement)
* [Prerequisites](#prerequisites)
* [Configure the project](#configure-the-project)
* [Run the project](#run-the-project)
* [Questions and comments](#questions-and-comments)
* [Contributing](#contributing)
* [Additional resources](#additional-resources)

Does your app show a people list that includes telephone numbers or Skype for Business Ids? How cool would it be if your
app could launch a new chat, audio, or video call in the Skype for Business client installed on the Android device? With the 
code in this sample, all you need to do is ask a user to pick a person from your list (along with the associated phone number or Skype address),
pick chat, audio, or video, and with a few lines of code, your app launches Skype in a new full screen activity. The call is already queued
with the phone number or id. 

##The code
Just add the following code from the sample into your app.


 ```java
        Button skypeButton = (Button) findViewById(R.id.button);
        final EditText SIPAddress = (EditText) findViewById(R.id.SIPAddress) ;
        final CheckBox videoCall = (CheckBox) findViewById(R.id.videoCheck);
        skypeButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {

                String uriString = "ms-sfb://call?id="+SIPAddress.getText().toString();
                if (videoCall.isChecked()){
                    uriString +="&video=true";
                }
                Uri uri = Uri.parse(uriString);
                Intent callIntent = new Intent(Intent.ACTION_VIEW, uri);
                startActivity(callIntent);
            }
        } );
 ```

##The sample

The sample has only a main activity with a text box and button. So simple.

![the main activity](images/SkypeCall.png)

##Device requirement
To run the Skype Android Mobile SDK samples project, your device must meet the following requirement:
* Android API level 17 or newer
* Skype for Business - Android App installed. Get [Skype for Business for Android](https://play.google.com/store/apps/details?id=com.microsoft.office.lync15&hl=en) from **Google Play**

###Prerequisites
To use the Skype Android Mobile SDK samples project, you need the following:
* The latest version of [Android Studio](http://developer.android.com/sdk/index.html).
* The [Gradle](http://www.gradle.org) build automation system version 2.2.1 or later.
* A Skype for Business or Skype for Business Online account. 
* [Java Development Kit (JDK) 7](http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html).

##Configure the project

1. Download or clone the [Skype-Android-Mobile-SDK-Samples](https://github.com/OfficeDev/Skype-for-Business-Android-Uri-Sample).
2. Start Android Studio.
3. From the **Welcome to Android Studio** dialog box, choose **Import project (Eclipse ADT, Gradle, etc)**.
4. Select the **settings.gradle** file in the **Skype-for-Business-Android-Uri-Sample** folder, and then click **OK**.
5. Respond to the dialog box ("Gradle Sync: Gradle settings for this project are not configured yet. Would you like the project to use the Gradle wrapper? ") by clicking the **OK** button to use the Gradle wrapper. 

##Run the project
After you've built the project you can run it on a device. Video calling is not currently supported on Android emulators.

1. Run the project.
2. Enter a telephone number with area code or enter a Skype for Business Id.
3. Optionally, check the _Video call_ checkbox.
4. Click the _MAKE SKYPE CALL_ button to start the call.

## Questions and comments
We'd love to get your feedback about the Android Skype-Android-Mobile-SDK-Samples. You can send your feedback to us in the [Issues](https://github.com/OfficeDev/Skype-for-Business-Android-Uri-Sample/issues) section of this repository. <br/>
General questions about Office 365 development should be posted to [Stack Overflow](http://stackoverflow.com/questions/tagged/Office365+API). Make sure that your questions are tagged with [Office365] and [API].

## Contributing
You will need to sign a [Contributor License Agreement](https://cla.microsoft.com/) before submitting your pull request. To complete the Contributor License Agreement (CLA), you will need to submit a request via the form and then electronically sign the CLA when you receive the email containing the link to the document. 

## Additional resources

* [Skype for Business - Mobile URIs documentation](https://msdn.microsoft.com/en-us/skype/skype-for-business-uris/sfbmobileuri)
* [Microsoft Office 365 API Tools](https://visualstudiogallery.msdn.microsoft.com/a15b85e6-69a7-4fdf-adda-a38066bb5155)
* [Office Dev Center for Skype](http://dev.office.com/skype)
* [Office 365 APIs starter projects and code samples](http://msdn.microsoft.com/en-us/office/office365/howto/starter-projects-and-code-samples)


## Copyright
Copyright (c) 2015 Microsoft. All rights reserved.
