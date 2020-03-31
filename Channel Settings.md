## **Channel Settings**

You are able to make basic settings for each channel in WinDarab.  
<p align="center">
<img src="images/Basic Channel Settings.jpg">
</p>
For each individual channel following settings are provided:  

*	Description
*	Format (numerical)
*	View Min
*	View Max
*	Signal (signal curve format)
*	Separate Bits

### **Making Channel Settings**

Select **“Tools&rarr; Settings&rarr; Channels”** in **Darab Ribbon** to open the “Channel Settings” dialog box.

<p align="center">
<img src="images/Channel List.jpg">
</p>

The Channels are divided into four channel list:

*	Measurements channels
*	Math channels
*	Internal channels
*	Temporary channels

Click on **Show measurements** button to **select and display** the **Measurements channels** list

<p align="center">
<img src="images/Measurement Channels.jpg">
</p>

Click on **Show math channels** button to **select and display** the **Math channels** list

<p align="center">
<img src="images/Math Channels.jpg">
</p>

Click on **Show internal channels** button to **select and display** the **Internal channels** list

<p align="center">
<img src="images/Internal Channels.jpg">
</p>

Click on Show temporary channels button to select and display the Temporary channels list
 
<p align="center">
<img src="images/temp channel.jpg">
</p>

Click on **Show/Hide all channels** button to **(de-)select and display/hide all channels**

<p align="center">
<img src="images/display channels.jpg">
</p>

For each channel in the lists the following settings can be defined:  
**Description** &nbsp; A description for the channel can be entered in the text field.  
**Format** &nbsp; Define the display format of numbers.
The following formats are provided in the **Format** combo box of each channel:

<p align="center">
<img src="images/format combo.jpg">
</p>

|||
|---|---|
|**View Min**|You can enter the value displayed as minimum for the channel.  
|**View Max**|You can enter the value displayed as maximum for the channel.  
|**Signal**|Determine the format for display of the signal curve.
The following formats are provided in the **Signal** combo box of each channel:  

<p align="center">
<img src="images/signal.jpg">
</p>

*    **Analog** - values are interpolated.
*	**Digital** - sampling points are represented by square wave signals
*	**Dotted** - each sampling point is represented by a dot
*  	**Bits** - each channel bit is interpreted as a separate signal and represented by a square wave signal

|||
|---|---|
|**Separate Bit**| With this option selected, single bit channels will be created for each bit of the measured channel. If selected each single bit will be shown as a channel.

You can now select each one of these bit-channels individually in the channels pane.

### **Importing Descriptions**
WinDarab enables you to import description for channels from a (named) object store.

Follow these steps to import a (named) object store:

1.	Open the “Channel Settings” box by using the “Tools/ Settings/ Channels” menu item.
2.	Click on “Import OSP/A2L”.
3.	Now select the (named) object store that contains the descriptions and click “OK”.
4.	The descriptions will now be imported.
5.	Click on “OK” to close the “Channel Settings” dialog box.

### **Channel Colors**
Select **“Tools&rarr; Settings&rarr; Program”** to open the Channel Colors Dialog

<p align="center">
<img src="images/Channel Colors Dialog.jpg">
</p>

This dialog allows you to assign different colors for different overlays to specific channels. The number of overlay-columns in the dialog equals the number of overlays in the File Explorer.  