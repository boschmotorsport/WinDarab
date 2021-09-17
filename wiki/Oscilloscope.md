# Oscilloscope

- [Oscilloscope](#oscilloscope)
  - [X Axis](#x-axis)
  - [Middle Click Window](#middle-click-window)
  - [Automatic Y Axis](#automatic-y-axis)
  - [Auto-align Telemetry and Logged Data](#auto-align-telemetry-and-logged-data)
  - [Show Extremas](#show-extremas)
  - [File Events](#file-events)
    - [Interacting with File Events](#interacting-with-file-events)

## X Axis

Settings for the X Axis can be found by **Right Clicking** anywhere on the X Axis scale.

From here you can control:

*  Start/End/Range of the X axis
*  Time in seconds or Distance in meters
*  Lap based x-axis (X Axis in lap distance or laptime)

<p align="center">
<img src="images/Oscilloscope - Settings.png">
</p>|

## Middle Click Window

Settings controlling the oscilloscope are available by **Middle Clicking** or **Left + Right Clicking**

<p align="center">
<img src="images/Oscilloscope - Middle Click Menu.png">
</p>|

From here you can control:

* Settings related to the selected Channel
* Settings related to the Zoom level
* Add/Remove Chart Areas
* Enable/Disable File Shifting (Click + drag an overlay)
* Define a File Shift in X-Axis units (seconds/meters)
* Align laptriggers of different overlays
* Set or Remove a Tag

## Automatic Y Axis

- After the user added a y-axis for a channel in the oscilloscope, the y-axis context menu can be used to turn the y-axis into an “automatic y-axis” (click “Selected channel” in the context menu)
- An automatic y-axis always shows the corresponding y-scale for the selected channel in this area.
- A second click on “Selected channel” REMOVES the automatic y-axis.
- If a channel is dropped onto an automatic y-axis, the y-axis is a normal axis for the channel.
- Note: A automatic axis always fills the complete height of the y-axis area and cannot be changed (height or vertical position).

<p align="center">
<img src="images/Oscilloscope Automatic Y Axis.jpg">
</p>

## Auto-align Telemetry and Logged Data

- If the option “Auto-Align running laps” is enabled all running laps of telemetry streams are automatically aligned and the oscilloscope is scrolled so that the aligned laptrigger is located at the left edge of the oscilloscope.
- As soon as the next laptrigger is received, the new lap is automatically aligned to the other laps.
- Note: While replaying the cursor is always moved to/for the overlay which is the closest to the right side of the oscilloscope. This ensures that all values (channels pane, analysis windows) are evaluated for the current values.


<p align="center">
<img src="images/Oscilloscope - Auto Align Laps.png">
</p>

## Show Extremas

### How to find it  <!-- omit in toc -->

1. Highlight Channel in Oscilloscope
  
|'D' key -> 'E' key | Channel Menu/Tab  |
|:---:|:---:|
|![Display Menu](images/Oscilloscope&#32;Display&#32;Menu&#32;Show&#32;Extremas.jpg) | ![Ribbon Menu](images/Ribbon&#32;Show&#32;Extremas&#32;Button.jpg) |

<p align="center">
<img src="images/Show Extremas Example.jpg">
</p>

## File Events

At the bottom of each oscilloscope there can be a collection of 'orbs', colored by overlay and event definition. These are time/distance markers for defined file events.

![File Event](images/Oscilloscope%20-%20File%20Event.jpg)

### Interacting with File Events

Left clicking on one of the events, the x-axis cursor will jump to the time/distance that the event occured.

Ctrl + N/P keys will jump to the (N)ext or (P)revious event relative to the current x-axis cursor position.
