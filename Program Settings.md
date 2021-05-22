# Program Settings

- [Program Settings](#program-settings)
  - [Colors](#colors)
    - [Color Theme](#color-theme)
  - [Measurement Window](#measurement-window)
    - [Single Value Per X Axis Point](#single-value-per-x-axis-point)
  - [Automatic Switch between x- or y- Axis Zoom](#automatic-switch-between-x--or-y--axis-zoom)
  - [Files and Folders](#files-and-folders)
    - [Folder Monitoring](#folder-monitoring)
    - [Lap Distance Normalization](#lap-distance-normalization)
      - [DIST Flag](#dist-flag)
    - [Data Compression](#data-compression)
  - [Miscellaneous](#miscellaneous)
  - [Telemetry](#telemetry)
    - [Activate WinDarab if Alarm Occurs](#activate-windarab-if-alarm-occurs)
    - [Network Adapters for Telemetry](#network-adapters-for-telemetry)
  - [Special Channels](#special-channels)
  - [Physical Units](#physical-units)
  - [Comments](#comments)
    - [File Open](#file-open)
    - [Outing Constants](#outing-constants)
  - [Import Defaults](#import-defaults)

<p align="center">
<img src="images/Program Settings - Getting There.png">
</p>

## Colors

<p align="center">
<img src="images/Program Settings - Colors.png">
</p>

Modify these settings to change the default colors of the WinDarab user interface

### Color Theme

To change to other pre-defined color themes, use the _Style_ Menu in the __Top Right__.

<p align="center">
<img src="images/Program Settings - Style Menu.png">
</p>

We generally recommend _Bosch Black_ for analysis

If you are in direct sunlight, _Bosch White_ will give better visibility

## Measurement Window

<p align="center">
<img src="images/Program Settings - Measurement Window.png">
</p>

### Single Value Per X Axis Point

When viewing very large data sets and you are zoomed out there are not enough pixels on the screen to represent each X axis point (time/distance). WinDarab can filter down the data and generate one value to represent a range of x axis points so that a single value can be plotted per pixel.

Setting Active:

<p align="center">
<img src="images/Program Settings - Single Value Per X Axis Point Active.png">
</p>

Setting Disabled:

<p align="center">
<img src="images/Program Settings - Single Value Per X Axis Point Inactive.png">
</p>

This setting only affects how the data is shown, underlying calculations (outing report/math channels/etc) are un-affected.

## Automatic Switch between x- or y- Axis Zoom

In many analysis windows Right Click and Hold + Mouse left/right or up/down will allow the user to adjust the zoom level.

If this setting is **disabled**:

- The initial movement of the mouse defines the zoom axis

If this setting is **enabled**:

- The final movement direct of the mouse defines the zoom axis

## Files and Folders

<p align="center">
<img src="images/Program Settings - Files and Folders.png">
</p>

### Folder Monitoring

WinDarab will monitor the file system for new data files. See [File System Monitoring](File%20Explorer#file-system-monitoring)

The default option is to monitor all folders where you open data from. If you have special sync folders on your machine, you can change to the 'This folder' setting and define it. (This is generally not needed)

### Lap Distance Normalization

WinDarab will, by default, try to normalize the distance of each lap to the currently selected racetrack.

- If you don't want the normalization to occur: select **Never**
- If you want each and every lap (in/out included) to be normalized: select **Always**
- If you want a definable deviation: enter it (5% is default)

#### DIST Flag

<p align="center">
<img src="images/File Explorer - DIST Flag.png"/>
</p>

This flag will appear in the File Explorer if:

- The lap length does not match the loaded trackmap

### Data Compression

If you want WinDarab to create compressed files when Exporting or Downloading from a logger, enable this setting.

- Opening compressed files is supported in 7.7.36 and higher versions.

## Miscellaneous

<p align="center">
<img src="images/Program Settings - Miscellaneous.png">
</p>

## Telemetry

<p align="center">
<img src="images/Program Settings - Telemetry.png">
</p>

### Activate WinDarab if Alarm Occurs

This setting will cause WinDarab to take the Focus if an alarm occurs.

### Network Adapters for Telemetry

You can define specific network adapters on your machine to look for WDServer

Most customer will not change this setting

## Special Channels

<p align="center">
<img src="images/Program Settings - Special Channels.png">
</p>

See the section [Special Channels](Special%20Channels)

## Physical Units

<p align="center">
<img src="images/Program Settings - Physical Units.png">
</p>

Users can define unit conversions if they prefer to work in non-standard units

## Comments

<p align="center">
<img src="images/Program Settings - Comments.png">
</p>

Comments can be added to each datafile. Use this dialog to define what file comments you would like to be able to write to each file.

Comments can be defined in the [Data Logger Import tool](Data%20Logger%20Import#comment-fields) or by highlighting an Outing Report then on the ribbon _Start_ &rarr; _Comments_

### File Open

Comments can be viewed for each file when in the File Open Dialog

<p align="center">
<img src="images/Program Settings - Comments and File Open Dialog.png">
</p>

### Outing Constants

Comments can be used for **File Constants** for use in Math Functions. However they are a bit clumsy for this task. 

- We recommend using [Setupsheets](Setupsheets) instead


## Import Defaults

<p align="center">
<img src="images/Program Settings - Import Defaults.png">
</p>

This dialog is for the much older import tool and will be depracated/removed in a later version of WinDarab.