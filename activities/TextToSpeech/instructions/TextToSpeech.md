# Activity: Text To Speech

### Background

This module demonstrates the use of Android’s TextToSpeech API. This API is utilized to programmatically convert text to speech.

A working version of this app is available at: https://github.com/milk-modules/Apps/tree/master/accessible/DemoApp05

### Prerequisite

1. Android Studio is installed on the development workstation
2. A working Android emulator is available for testing
3. TalkBack is enabled on the emulator (instructions: https://milk-modules.github.io/activities/general/Android_TalkBack_Install.pdf)

### Steps

This activity will utilize a pre-created version of this project and only applies the TextToSpeech functionality. Download the code for DemoApp05 from: https://github.com/milk-modules/Apps/tree/master/non-accessible

The project contains only one screen (activity). The primary user interface (UI) elements of this screen are:

{0}.	A Switch control located at the top of the screen. Turning this control ‘on’ and ‘off’ will hide/show the UI elements on the screen. This behavior is to simulate a blind user.
{0}.	Two Buttons. One button is to obtain the current date and the other button is to obtain the current time.
{0}.	A TextView located towards the bottom of the screen. This control will show the date and time when the button is tapped/clicked.

The existing project contains the code to show the date and time when the buttons are tapped/clicked.

Follow the below steps to add TextToSpeech functionality so that when a button is tapped/clicked, the app will announce/speak the date and time. The file MainActivity.java should be updated with the below.


1. Create the following variable:

   ```java
   private TextToSpeech textToSpeech;
   ```

2. Add the following method:

   ```java
   private void provideMessage(final String message){
       AccessibilityManager accessibilityManager = (AccessibilityManager) getSystemService(ACCESSIBILITY_SERVICE);
       boolean isAccessibilityEnabled = accessibilityManager.isEnabled();
       boolean isExploreByTouchEnabled = accessibilityManager.isTouchExplorationEnabled();

       if (isAccessibilityEnabled && isExploreByTouchEnabled){
           textToSpeech = new TextToSpeech(MainActivity.this, new TextToSpeech.OnInitListener() {
               @Override
               public void onInit(int status) {
                   if(Build.VERSION.SDK_INT >= Build.VERSION_CODES.LOLLIPOP){
                       textToSpeech.speak(message, TextToSpeech.QUEUE_FLUSH, null, null);
                   }
                   else{
                       textToSpeech.speak(message, TextToSpeech.QUEUE_FLUSH, null);
                   }
               }
           });
       }

       txtDisplay.setText(message);
   }
   ```

3. Update the handler for the two buttons:

   ```java
   a.	Replace: txtDisplay.setText("Today's Date: " + todayDateString);
   With: provideMessage("Today's Date: " + todayDateString);

   b.	Replace: txtDisplay.setText("Current Time: " + currentTimeString);
   With:	provideMessage("Current Time: " + currentTimeString);
   ```

   ​

The purpose of the method *provideMessage* is to utilize Android’s TextToSpeech API to announce the date and time. The method only calls the API if the accessibility and talk back is enabled.  
