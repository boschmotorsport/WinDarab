# Compare Overlays

In WinDarab it is possible to compare multiple overlays in multiple ways.

- [Compare Overlays](#compare-overlays)
  - [Overlays Setup](#overlays-setup)
    - [Add Overlays](#add-overlays)
    - [Delete Overlays](#delete-overlays)
    - [Change Overlay Selection](#change-overlay-selection)
    - [Show/Hide Overlays](#showhide-overlays)
  - [Oscilloscope](#oscilloscope)
    - [Compare two overlay differences](#compare-two-overlay-differences)
    - [Remove Overlay from Oscilloscope](#remove-overlay-from-oscilloscope)
  
## Overlays Setup

### Add Overlays

Overlays can be created in the File Explorer Window with one or more files open.
To create multiple overlays:
- Select __Overlay/Add__
  
![Select Add Overlay](images/Overlays%20Select%20Add.jpg)

or
- Right click an overlay __Orb/New Overlay/Add__
  
![Orb Add Overlay](image/../images/Overlays&#32;Orb&#32;Add.jpg)

Now with multiple Overlays added:

![Multiple Overlays](images/Overlays&#32;Multiple.jpg)

### Delete Overlays

Overlays may be deleted by two methods:
- Select __Overlay/Delete__

![Select Delete Overlay](images/Overlays%20Select%20Delete.jpg)

or

- Right click an overlay __Orb/New Overlay/Delete__

![Orb Delete Overlay](images/Overlays&#32;Orb&#32;Delete.jpg)

### Change Overlay Selection

Files selected for overlays can be changed in the File Explorer Window by clicking in the grid where no overlay is currently set:

![Change Overlay](images/Overlays&#32;Change&#32;File.jpg)

### Show/Hide Overlays

Overlays can be shown or hidden without adding and deleting the overlay recreating settings. TO do so right click on the overlay and toggle Show Overlay:

![Show Hide Overlays](images/Overlays&#32;Show&#32;Hide.jpg)
 
## Oscilloscope

Both overlays will show in the Oscilloscope Window by default.

### Compare two overlay differences

Overlays can be compared with the diffence in values shown. This is especially useful when doing a comparison of two drivers.

- Set the base Overlay by right clicking on the overlay orb then selecting __Use as base for differences__

![Set Base Overlay](images/Overlays&#32;Set&#32;Base&#32;File.jpg)

- Show the channel as a difference by right clicking on the channel value then selecting __Use as diff-channel__

![Set Diff Channel](images/Overlays&#32;Set&#32;Lapdiff.jpg)

An example outcome for looking at laptime gain/loss:

![Laptime Gain Loss Example](images/Overlays&#32;Laptime&#32;Comparison.jpg)

### Remove Overlay from Oscilloscope

To remove an overlay value from an oscilloscope:

- Click the value of the overlay you wish to remove from this area then press d elete on the keyboard

or

- Right click the value of the overlay you wish to remove from this area and click __Remove__