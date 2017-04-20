<!---
  category: Holographic
  samplefwlink: http://go.microsoft.com/fwlink/p/?LinkId=847281
--->

# Spatial interaction source sample

Shows how to use the different kind of SpatialInteractionSource such as Hand on HoloLens or
Six Degree of Freedom (6DOF) Controllers on Windows Mixed Reality Desktop:
- track the location of the source
- handle user interactions such as gestures or actions on the controller's buttons.

> **Note:** This sample is part of a large collection of UWP feature samples. 
> If you are unfamiliar with Git and GitHub, you can download the entire collection as a 
> [ZIP file](https://github.com/Microsoft/Windows-universal-samples/archive/master.zip), but be 
> sure to unzip everything to access shared dependencies. For more info on working with the ZIP file, 
> the samples collection, and GitHub, see [Get the UWP samples from GitHub](https://aka.ms/ovu2uq). 
> For more samples, see the [Samples portal](https://aka.ms/winsamples) on the Windows Dev Center. 

A small tile representing a drawing tool is displayed at the spatial location of each
detected SpatialInteractionSource. By moving this source while pressing its Select button (Controller)
or keeping the finger down, the user can draw a stroke, which is generated by joining
the successive locations of the drawing tool (see below).

A tap without moving (Hand) or a press on the Menu button (Controller) displays a carousel of tools
which allows the user to change the color or the size of the drawing tool associated to the source
or to clear the whole drawing.

### HoloLens

All interactions are triggered by Hand:
- Air Tap switches between modes and select tools
- In drawing mode, a Manipulation gesture draws a stroke on the board, starting at the location
  where the user is gazing at.
- in tool selection mode, a Navigation gesture turns the carousel and selects another tool

### Windows Mixed Reality Desktop

Interactions are triggered by 6DOF Controllers
- Menu button switches from drawing mode to tool selection mode
- In drawing mode, pressing the Select button and moving the controller draws a stroke: the stroke can be drawn
  in front of the controller or on a board, depending whether the controller is pointing to the board or not.
- In tool selection mode, pressing the Select button validates the tool selection
- In tool selection mode, using the controller's Thumbstick or Touchpad turns the carousel

### Additional remarks

**Note** The Windows universal samples for Windows 10 Holographic require Visual Studio 2017
to build, and either a Windows Holographic device or a Windows Mixed Reality Headset with
at least one 6DOF controller to execute. Windows Holographic devices include the
Microsoft HoloLens and the Microsoft HoloLens Emulator.

To obtain information about Windows 10 development, go to the [Windows Dev Center](http://go.microsoft.com/fwlink/?LinkID=532421).

To obtain information about the tools used for Windows Holographic development, including
Microsoft Visual Studio 2017 and the Microsoft HoloLens Emulator, go to
[Install the tools](https://developer.microsoft.com/windows/holographic/install_the_tools).

## Related topics

### Reference

The following types are used in this code sample:
* [Windows.UI.Input.Spatial](https://docs.microsoft.com/en-us/uwp/api/Windows.UI.Input.Spatial)
  * [SpatialGestureRecognizer class](https://docs.microsoft.com/en-us/uwp/api/windows.ui.input.spatial.spatialgesturerecognizer)
  * [SpatialInteractionManager class](https://docs.microsoft.com/en-us/uwp/api/windows.ui.input.spatial.spatialinteractionmanager)
  * [SpatialInteractionSource class](https://docs.microsoft.com/en-us/uwp/api/windows.ui.input.spatial.spatialinteractionsource)
  * [SpatialInteractionSourceState class](https://docs.microsoft.com/en-us/uwp/api/windows.ui.input.spatial.spatialinteractionsourcestate)
  * [SpatialInteractionSourceProperties class](https://docs.microsoft.com/en-us/uwp/api/windows.ui.input.spatial.spatialinteractionsourceproperties)
  * [SpatialInteractionSourceLocation class](https://docs.microsoft.com/en-us/uwp/api/windows.ui.input.spatial.spatialinteractionsourcelocation)
  * [SpatialPointerInteractionSourcePose class](https://docs.microsoft.com/en-us/uwp/api/windows.ui.input.spatial.spatialpointerinteractionsourcepose)
  * [SpatialInteractionControllerProperties class](https://docs.microsoft.com/en-us/uwp/api/windows.ui.input.spatial.spatialinteractioncontrollerproperties)
  * [SpatialInteractionController class](https://docs.microsoft.com/en-us/uwp/api/windows.ui.input.spatial.spatialinteractioncontroller)
  * [SpatialInteractionPressKind enum](https://docs.microsoft.com/en-us/uwp/api/windows.ui.input.spatial.spatialinteractionpresskind)
  * [SpatialInteractionSourceKind enum](https://docs.microsoft.com/en-us/uwp/api/windows.ui.input.spatial.spatialinteractionsourcekind)
  * [SpatialGestureSettings enum](https://docs.microsoft.com/en-us/uwp/api/windows.ui.input.spatial.spatialgesturesettings)
* [Windows.Devices.Haptics](https://docs.microsoft.com/en-us/uwp/api/windows.devices.haptics)
  * [SimpleHapticsController class](https://docs.microsoft.com/en-us/uwp/api/windows.devices.haptics.simplehapticscontroller)
  * [SimpleHapticsControllerFeedback class](https://docs.microsoft.com/en-us/uwp/api/windows.devices.haptics.simplehapticscontrollerfeedback)
  * [KnownSimpleHapticsControllerWaveforms class](https://docs.microsoft.com/en-us/uwp/api/windows.devices.haptics.simplehapticscontrollerfeedback)

## System requirements

**Client:** Windows 10 build 15063, HoloLens or Mixed Reality Development Kit

**Phone:** Not supported

## Build the sample

1. If you download the samples ZIP, be sure to unzip the entire archive, not just the folder with
   the sample you want to build.
2. Start Microsoft Visual Studio 2017 and select **File** \> **Open** \> **Project/Solution**.
3. Starting in the folder where you unzipped the samples, go to the Samples subfolder, then the
   subfolder for this specific sample, then the subfolder for your preferred language (C++, C#, or
   JavaScript). Double-click the Visual Studio 2017 Solution (.sln) file.
4. Press Ctrl+Shift+B, or select **Build** \> **Build Solution**.

## Run the sample

The next steps depend on whether you just want to deploy the sample or you want to both deploy and
run it.

### Deploying the sample to the Microsoft HoloLens emulator

- Click the debug target drop-down, and select **Microsoft HoloLens Emulator**.
- Select **Build** \> **Deploy** Solution.

### Deploying the sample to a Microsoft HoloLens

- Developer unlock your Microsoft HoloLens. For instructions, go to [Enable your device for development]
  (https://msdn.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#enable-your-windows-10-devices).
- Find the IP address of your Microsoft HoloLens. The IP address can be found in **Settings**
  \> **Network & Internet** \> **Wi-Fi** \> **Advanced options**. Or, you can ask Cortana for this
  information by saying: "Hey Cortana, what's my IP address?"
- Right-click on your project in Visual Studio, and then select **Properties**.
- In the Debugging pane, click the drop-down and select **Remote Machine**.
- Enter the IP address of your Microsoft HoloLens into the field labelled **Machine Name**.
- Click **OK**.
- Select **Build** \> **Deploy** Solution.

### Pairing your developer-unlocked Microsoft HoloLens with Visual Studio

The first time you deploy from your development PC to your developer-unlocked Microsoft HoloLens,
you will need to use a PIN to pair your PC with the Microsoft HoloLens.
- When you select **Build** \> **Deploy Solution**, a dialog box will appear for Visual Studio to
  accept the PIN.
- On your Microsoft HoloLens, go to **Settings** \> **Update** \> **For developers**, and click on
  **Pair**.
- Type the PIN displayed by your Microsoft HoloLens into the Visual Studio dialog box and click
  **OK**.
- On your Microsoft HoloLens, select **Done** to accept the pairing.
- The solution will then start to deploy.

### Deploying and running the sample

- To debug the sample and then run it, follow the steps listed above to connect your
  developer-unlocked Microsoft HoloLens, then press F5 or select **Debug** \> **Start Debugging**.
  To run  the sample without debugging, press Ctrl+F5 or select **Debug** \> **Start Without Debugging**.