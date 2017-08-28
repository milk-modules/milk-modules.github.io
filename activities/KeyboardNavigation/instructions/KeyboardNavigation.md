# Activity: Keyboard Navigation

### Background

This module demonstrates the use of an external keyboard or D-Pad to navigate around an app.

A working version of this app is available at: https://github.com/milk-modules/Apps/tree/master/accessible/DemoApp04

### Prerequisite

1. Android Studio is installed on the development workstation
2. A working Android emulator is available for testing
3. The emulator has been configured to use a D-Pad

### Steps

This activity will utilize a pre-created version of this project and only applies associating focus properties to the UI controls. Download the code for DemoApp04 from: https://github.com/milk-modules/Apps/tree/master/non-accessible

The project contains only one screen (activity). The primary user interface (UI) elements of this screen are:

{0}.	A form containing text boxes, buttons and a list.
  [Note: there is no functionality associated with the button clicks]


Follow the below steps to associate the focus attributes to the UI controls. All updates below are to be done on the file: ***activity_main.xml***

1. Update the ‘*editTextName* ’ property listing with the following:

   ```xml
   <EditText
       android:id="@+id/editTextName"
       android:layout_width="wrap_content"
       android:layout_height="wrap_content"
       android:layout_weight="0.71"
       android:ems="10"
       android:inputType="textPersonName"
       android:nextFocusDown="@+id/listViewOrigin"
       android:nextFocusLeft="@+id/buttonSave"
       android:nextFocusRight="@+id/listViewOrigin"/>
   ```

2. Update the ‘*listViewOrigin*’ property listing with the following:

   ```xml
   <ListView
       android:id="@+id/listViewOrigin"
       android:layout_width="241dp"
       android:layout_height="match_parent"
       android:entries="@array/country_origin"
       android:nextFocusLeft="@+id/editTextName"
       android:nextFocusRight="@+id/editTextQuantity"/>
   ```

3. Update the ‘*editTextQuantity* ’ property listing with the following:

   ```xml
   <EditText
       android:id="@+id/editTextQuantity"
       android:layout_width="wrap_content"
       android:layout_height="wrap_content"
       android:layout_weight="0.61"
       android:ems="10"
       android:inputType="number"
       android:nextFocusRight="@+id/buttonCancel"
       android:nextFocusLeft="@+id/listViewOrigin"
       android:nextFocusUp="@+id/listViewOrigin"
       android:nextFocusDown="@+id/buttonCancel"/>
   ```

4. Update the ‘*buttonCancel*’ property listing with the following:

   ```xml
   <Button
       android:id="@+id/buttonCancel"
       android:layout_width="wrap_content"
       android:layout_height="wrap_content"
       android:layout_weight="1"
       android:text="Cancel"
       android:nextFocusRight="@+id/buttonSave"
       android:nextFocusUp="@+id/editTextQuantity"
       android:nextFocusLeft="@+id/editTextQuantity"
       android:nextFocusDown="@+id/buttonSave"/>
   ```

5. Update the ‘*buttonSave*’ property listing with the following:

   ```xml
   <Button
       android:id="@+id/buttonSave"
       android:layout_width="wrap_content"
       android:layout_height="wrap_content"
       android:layout_weight="1"
       android:text="Save"
       android:nextFocusRight="@+id/editTextName"
       android:nextFocusUp="@+id/buttonCancel"
       android:nextFocusLeft="@+id/buttonCancel"
       android:nextFocusDown="@+id/editTextName"/>
   ```

   ​

Deploy the app into the emulator and use the arrow keys associated with the D-Pad to access the UI elements in the screen instead of touching the controls or using a mouse pointer. 
