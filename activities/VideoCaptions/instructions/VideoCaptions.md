# Activity: Video Captions

### Background

This module demonstrates the use of Android’s video captioning feature. When this feature is enabled, captions associated with videos are shown when the video plays.

A working version of this app is available at: https://github.com/milk-modules/Apps/tree/master/accessible/DemoApp07

### Prerequisite

1. Android Studio is installed on the development workstation
2. A working Android emulator is available for testing
3. The captioning accessibility feature is enabled on the emulator (instructions:  https://support.google.com/accessibility/android/answer/6006554)

### Steps

This activity will utilize a pre-created version of this project and only applies associating captions with the video player. Download the code for DemoApp07 from: https://github.com/milk-modules/Apps/tree/master/non-accessible

The project contains only one screen (activity). The primary user interface (UI) elements of this screen are:

- A Switch control located at the top of the screen. Turning this control ‘on’ and ‘off’ will mute/unmute the video volume and hide/show captions. This behavior is to simulate a a deaf or hard-of-hearing user

- Play button to play the video

The existing project contains the code to play the video and mute/unmute the volume

Follow the below steps to associate the captions file to the video so that when the accessibility mode is enabled the captions will be shown

1. 1.	Insert the following code at line #45 in '*MainActivity.java*':

   ```java
   //captions file
   InputStream subs =  getResources().openRawResource(R.raw.sample_video_caption);
   videoView.addSubtitleSource(subs, MediaFormat.createSubtitleFormat("text/vtt", Locale.ENGLISH.getLanguage()));
   ```
