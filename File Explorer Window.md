## File Explorer Window
The File Explorer Window displays and manages all logger data files opened in the File Explorer (see chapter File Explorer). WinDarab supports the following logger files:

* WinDarab 7 Files
* WinDarab 6 Files
* WDServer Telemetry Files
* Linked Files
* MDF Files
* MSX Files

Open File Explorer Window 
Beschreibung: LinkeMaustaste
 Select **Windows &rarr; Dockable windows &rarr; Files** from Darab Ribbon to open the **File Explorer Window**.

<p align="center">
<img src="images/File Explorer Button.jpg">
</p>
 </br>
 </br>
<p align="center">
<img src="images/File Explorer Window.jpg">
</p>
 
The File Explorer Window is a dockable window. It contains a toolbar and a WinDarab file list window.
 
### [File Explorer Window Toolbar](file-explorer-window-toolbar)
<table>
<tr>
<td><p align="center">
<img src="images/File Explorer Open File Button.jpg">
</p></td><td>Opens the File Explorer (see File Explorer)</td></tr>
 
<tr>
<td><p align="center">
<img src="images/File Explorer Close File Button.jpg">
</p></td><td>Close the selected file.</td></tr>
 
<tr>
<td><p align="center">
<img src="images/File Explorer Create Overlay Button.jpg">
</p></td><td>Create an overlay to compare files/laps (see Overlay). Each overlay is displayed in a different color.</td></tr>
 
<tr>
<td><p align="center">
<img src="images/File Explorer Zoom Fast Laps Button.jpg">
</p></td><td>Zoom and compare fastest laps of each overlay.</td></tr>
 
<tr>
<td><p align="center">
<img src="images/File Explorer Overlay Color Button.jpg">
</p></td><td>Change the color of the selected overlay</td></tr>
 
<tr>
<td><p align="center">
<img src="images/File Explorer Reduce Lap List Button.jpg">
</p></td><td>Reduce the lap list. The "outing #"- line under the file name in the file list will not be displayed.</td></tr>
</table>
 
### [File Explorer Window File List](file-explorer-window-file-list)
The file list contains a list of all opened files in the File Explorer.

<p align="center">
<img src="images/File Explorer Window List.jpg">
</p>

Under the file name the outing number is displayed. The laps are listed under the outing number. Each lap is indicated with a lap number and a lap time. The fastest lap is marked with the label Beschreibung: <img src="images/FAST.jpg">. If an overlay is assigned to a lap it is displayed by a colored point before the lap number.

<table><tr><td><b>Hint:</b></td>
<td>If the menu point "Reduce lap list" is selected the line "Outing #" will be hidden.</td></tr></table>
 

### [File Explorer Window Context Menu](file-explorer-window-context-menu)

After right-click on an item in the File Explorer window a context menu opens. The context menu contains the following options (some variations depending on file or lap is highlighted):

<p align="center">
<img src="images/File Explorer Right Click Context Menu.jpg">
</p>
<table>
<tr><td>Open</td>
<td>Opens a new file.</td></tr>

<tr><td>Append</td>
<td>Opens a new file and appends it to the selected lap.</td></tr>

<tr><td>Replace</td>
<td>With this menu-item, you can replace the file by another file. After clicking on the item, the open-file-dialog opens, where you can select the file replacing the file in the file-explorer.</td></tr>

<tr><td>Setupsheet</td>
<td>Open the setupsheet editor</td></tr>

<tr><td>Out-Lap</td>
<td>Sets the "Outlap" flag on the selected lap</td></tr>

<tr><td>In-Lap</td>
<td>Sets the "Inlap" flag on the selected lap</td></tr>

<tr><td>Ignore as fastest Lap</td>
<td>Ignore the currently selected lap as "Fastest Lap"</td></tr>

<tr><td>Renumber</td>
<td>Opens a sub-menu to provide options for renumbering laps (alters the lap-stack)
This is useful with missed beacons or manually inserted</td></tr>

<tr><td>Close</td>
<td>You can use the close menu item to close this file.</td></tr>

<tr><td>Fastest laps</td>
<td>Zoom and compare fastest laps of each overlay.</td></tr>

<tr><td>Reduce lap list</td>
<td>Reduce the lap list. The "outing #"- line under the file name in the file list will not be displayed.</td></tr>
</table>

## [Overlay](overlay)
Overlay provides the possibility to compare laps/files and to add a lap/file to an oscilloscope (see chapter Oscilloscope). Overlays are displayed as points in different colors.

<p align="center">
<img src="images/Overlays.jpg">
</p>

By default at least one overlay exists in the File Explorer Window. If you open a file in the File Explorer (see chapter File Explorer) the overlay is assigned to the fastest lap of the file.
 
#### [Overlay Context Menu](overlay-context-menu)
<table><tr><td><b>Hint:</b></td>
<td>Click with the right mouse button on one overlay point or the overlay row to open the overlay context menu.</td></tr></table>

<p align="center">
<img src="images/Overlay Context Menu.jpg">
</p>

<table>
<tr><td>Add</td>
<td>Add an overlay in the overlay list under the File Explorer window toolbar. If at least one file is opened in the File Explorer window the overlay is assigned to the next longer lasting lap without overlay in the first file of the list. If each lap has an assigned overlay already all subsequent overlays will be assigned to the longest lap in the first file.</td></tr>

<tr><td>Show overlay</td>
<td>Globally hides this overlay and all associated channels</td></tr>

<tr><td>Replace file</td>
<td>Replace the file of the selected overlay. The File Explorer is opened and allows you to select the new file.</td></tr>
 
<tr><td>Detach file</td>
<td>Detach the file from the overlay. After this, the overlay has no file.</td></tr>
 
<tr><td>Change color</td>
<td>A color palette is opened that allows you to select the color of the selected overlay.</td></tr>

<tr><td>Overlay Coloring</td>
<td>Allow selected overlay to use the global selection for channel coloring or override it<td></tr>

<tr><td>Delete</td>
<td>Select this menu point to delete the overlay.</td></tr>

<tr><td>Pin lap</td>
<td>Pin this lap, scrolling the cursor will stop at the lap end. Can also be used to set a base file for referencing when looking at telemetry on another overlay</td></tr>
 
<tr><td>Use as x-axis overlay</td>
<td>Select this option to use this overlay as base-overlay for the x-axis.</td></tr>
 
<tr><td>Use as base for differences</td>
<td>Select this option to use this overlay as the base-overlay for difference-channels (comparing 2+ overlays).</td></tr>
</table>

## [Drag and Drop](drag-and-drop)
Files can be opened by dragging them from your windows file system into the WinDarab FileExplorer. Depending on the location where you drop the file, the file can be added to the file-list, replace an other file or replace an overlay.

<table>
<tr><td>Adding a file</td>
<td>You can add a file to the file-list by dropping it anywhere on the list but an existing filename or overhead-column. Your files will be added to the list. If you add more than one file to the list, as default, they will be added as  one file. To open more files as single files, press Ctrl while dropping the files.</td></tr>
 
<tr><td>Adding a file to a Filegroup</td>
<td>You can add one or more files to a filegroup by dropping them over an existing file. When you drag the files over an existing file, the target is highlighted to show that you can add the files.</td></tr>
 
<tr><td>Replacing a file</td>
<td>You can replace one or more files by dropping a file over an existing file while pressing the Shift-key. When you drag the files over an existing file, the target is highlighted to show that it can be replaced.</td></tr>
 
<tr><td>Replacing an overlay</td>
<td>Dropping a file on an overlay-column adds the file to the file-list and assigns the columns overlay-color to the new added file. If this removes the last overlay from a file, this file will be removed. </td></tr>
</table>

## [File System Monitoring](file-system-monitoring)
When a file is opened in the file explorer, the containing folder as well as all of his sub folders are monitored for new darab files. When a new darab file is created in a monitored folder, darab shows a balloon tip to let the user know that a new file was created.

<p align="center">
<img src="images/File System Monitoring.jpg">
</p>

In addition to this balloon tip, a region on the bottom side of the file explorer is created where all new files are listet. 

<p align="center">
<img src="images/File System Monitoring Region.jpg">
</p>

You can open these files by dragging them into the file explorer (see Drag and Drop) or by using the contextmenu.
 
<table><tr><td><b>Hint:</b></td>
<td>The separator between the new files and the file explorer can be dragged to reduce the size of the region. You also can minimize/maximize the region with a double-click on the separator.</td></tr></table>
 

 

