# Program Start

- [Program Start](#program-start)
  - [Important Tips](#important-tips)
  - [Changing The Color Style](#changing-the-color-style)
  - [License](#license)
  - [**Command Line**](#command-line)
    - [-d \<workdesk file>](#-d-workdesk-file)
    - [-f &lt;filename> [-f \<filename> …]](#-f-filename--f-filename-)

After starting WinDarab the user interface appears in which the last edited desktop (see chapter Desktop) or new desktop is opened. A new desktop will open if WinDarab is started the first time.

WinDarab offers a structured user interface with several components:

|![User Interface](images/Structured&#32;User&#32;Interface&#32;-&#32;Color&#32;Highlighted.jpg)|
|---|
|This is a possible view of composition of the WinDarab components. You can configure the WinDarab components so that the view complies with your operation methods.|

![User Interface](images/Structured&#32;User&#32;Interface&#32;-&#32;Explanations.jpg)
Further description of the different components for the shown arrangement:

- **File Explorer** window displayed upper left contains the list of opened logger data files.
- **Racetrack** window placed bottom left shows the current racetrack and course segmentation.
- **Channels** window arranged upper right displays a list of measurement, mathematical, internal or temporary channels according to the users’ choice.
- **Color** window arranged bottom right allows you to pick a color for an element (for instance a channel in an analysis window).
- **Oscilloscope**, **Analysis** Window, **Instrument Panel** resides in the middle of WinDarab and represents data or results of the calculations that are performed.

## Important Tips

Keyboard

- Right next to some menu items you will also see keystroke combinations that allow you to perform functions from your keyboard. Using your keyboard rather than the mouse to execute frequently used functions saves a great deal of time.

Context Menu

- The context menu of an element (window, channel etc.) contains a list of frequently used and useful functions. It is opened by clicking with the right mouse button on the element. In case the element has a zoom function, the context menu is opened by using the *middle mouse button*, or the *left and right mouse buttons*.

## Changing The Color Style

|![Available Style](images/Available&#32;Styles.jpg)|You can change the sytle of your WinDarab7 by clicking on the *Style* menu in the top right of the window and then choose a style from the drop-down.|
|---|---|

## License

If you want to update your WinDarab license, you can do this by clicking on **WinDarab-Orb** &rarr; **Tools** &rarr; **Update license**
<p align="center">
<img src="images/License Menu.jpg">
 </p>
From here on just follow the instructions. There are two ways to install a new WinDarab license.

1. You can insert a license file (.lic)

2. You can insert a license number. *For this option you have to be connected to the internet*

To check your license information, just click on **WinDarab-Orb** &rarr; **Tools** &rarr; **Show license information**

## **Command Line**

Following command line arguments may be passed to WinDarab on start up.

### -d \<workdesk file>

Opens WinDarab using the given workdesk file. If no additional data files are passed the saved workdesk is completely restored – including the used files and zoom.

If the argument is not used WinDarab loads the workdesk which was saved by WinDarab during shutdown of the application.

### -f &lt;filename> [-f \<filename> …]

Use the –f argument to pass one (or more) data files which are opened instead of the files within the workdesk.

In front of each file name the argument –f has to be provided!

**Note:**  
Don't forget to put filenames inside of two quotes ("<path/filename>") if the path or filename contains space characters.  
You may use quotes at any time to prevent misinterpreting the command line arguments.
