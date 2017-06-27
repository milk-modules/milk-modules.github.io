# Color blind accessibility android app

1. Install Android Studio from these instructions. (It will take a few minutes to install.)

2.Download the code from http://bit.ly/2q3pxgt.

You can also view the code on GitHub here: https://github.com/milkmodules/Apps/tree/master/non-accessible/DemoApp02-BalloonSimple

3. Extract the zip file into a directory on the C: drive.
<img style="margin:10px;" src="https://github.com/milk-modules/milk-modules.github.io/blob/master/images/readme/image1.png" alt="Image">

4. Import project in to Android studio
a. Open Android studio.
b. Import project in Android studio

<img style="margin:10px;" src="https://github.com/milk-modules/milk-modules.github.io/blob/master/images/readme/image2.png" alt="Image">

c. Open the directory you unzipped the activity into.
5. Run the project using the emulator.

<img style="margin:10px;" src="https://github.com/milk-modules/milk-modules.github.io/blob/master/images/readme/image3.png" alt="Image">

a. Once the emulator starts up, select the “balloon game” app on the Apps screen.
6. You will be able to see an app that is non-accessible to color-blind users.

<img style="margin:10px;" src="https://github.com/milk-modules/milk-modules.github.io/blob/master/images/readme/image4.png" alt="Image">

7. To fix this follow the following steps:
a. Open Circle.java file
b. On line 36, paste the following code

```java

if(isPoppable) {
 Paint paint = new Paint();
 paint.setColor(textColor);
 paint.setTextSize(64f);
 paint.setAntiAlias(true);
 paint.setTextAlign(Paint.Align.CENTER);
 canvas.drawText("+", x, y + circleRadius / 2, paint);
}

```

c. Run the project again and see the difference.

<img style="margin:10px;" src="https://github.com/milk-modules/milk-modules.github.io/blob/master/images/readme/image5.png" alt="Image">

### Troubleshooting:
When you first open the project, you may be unable to run it because of this error:

<img style="margin:10px;" src="https://github.com/milk-modules/milk-modules.github.io/blob/master/images/readme/image6.png" alt="Image">

Click on the blue text and select “Accept” and then “Install” on the popup. 
