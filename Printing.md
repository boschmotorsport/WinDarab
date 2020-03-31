## **Printing**

You can generate print previews for and print Logged Data as well as Analysis Windows.

**Note:**  
It could be possible that very fine lines will not be displayed in the print preview. This may be a result of a discrepancy between your screen and printer resolution.
The lines will nonetheless be visible when printed.

If you choose your colors please consider that background colors will not be printed. For example light colors against a black background are easy to see on screen, but your printed output will be difficult to read.


### **Print Optons**

Before a print job starts printing, or before the Print Preview appears on your screen, WinDarab will display a dialog box with printing options.

#### **”Layout” Tab**

<p align="center">
<img src="images/print layout.jpg">
</p>

If more than one print layout is available for the window you want to print you can select the desired layout in this tab.

#### **”Logged Data” Tab**

<p align="center">
<img src="images/Logged Data Tab.jpg">
</p>

Use this tab to determine the details you want an Oscilloscope to contain for printing.

### **Print Preview**

Use these steps to print a window:

   1. Arrange the window you want to print so that the data will be displayed in the desired form.
   2. Select **“WinDarab-Button&rarr; Print&rarr; Print Preview”** from the menu
   3. A selection of available templates for printing windows now appears. Choose the template you want.
   4. The “Print Preview” window will now be displayed.  
   5.  Use this window to  
       * set a zoom factor (10 - 400%)
       * print a template
       * close the window

### **Print**

Follow these steps to print a window directly:

Arrange the window you want to print so that the data is displayed in the desired form.  
Select **“WinDarab-Button&rarr; Print&rarr; Print”** from the menu.  
A selection of available templates may now appear. Choose the template you want.  
The Windows “Print” dialog box appears next.  
Click on “OK”.  
The template you have chosen will now be printed.

**Note:**  
The Windows “Print” dialog box will only permit you to select your printer; all other settings have no effect. 

### **Command Line**

Following command line arguments may be passed to WinDarab on start up.

#### **-d&lt;workdesk file&gt;**  
Opens WinDarab using the given workdesk file. If no additional data files are passed the saved workdesk is completely restored – including the used files and zoom.

If the argument is not used WinDarab loads the workdesk which was saved by WinDarab during shutdown of the application.

#### **-f &lt;filename> [-f &lt;filename&gt; …]**  
Use the –f argument to pass one (or more) data files which are opened instead of the files within the workdesk.

In front of each file name the argument –f has to be provided!

**Note:**  
Don't forget to put filenames inside of two quotes ("<path/filename>") if the path or filename contains space characters.  
You may use quotes at any time to prevent misinterpreting the command line arguments.   