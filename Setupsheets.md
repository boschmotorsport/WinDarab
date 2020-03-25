# Setupsheets

In WinDarab vehicle setupsheets can be created and maintained to correlate data with car changes. Setupsheet values can be used in data analysis for viewing and calculations.

- [Setupsheets](#setupsheets)
  - [Setupsheet Creation](#setupsheet-creation)
    - [Manual Creation](#manual-creation)
    - [Programmatic Creation](#programmatic-creation)
  - [Using Setupsheet values](#using-setupsheet-values)
    - [Using Values in Plots and Math](#using-values-in-plots-and-math)
    - [Changing existing Setupsheets](#changing-existing-setupsheets)
  - [Example: Programmatic Setupsheet Creation](#example-programmatic-setupsheet-creation)
  
## Setupsheet Creation
There are two main ways to create setupsheets. Setupsheets can be created in WinDarab throught the built in GUI manually or programmatically from an existing Excel sheet or other source.

### Manual Creation
To create a setupsheet click on the Setupsheet icon in the ribbon under Tools->Mathematics.

![Setupsheet Icon Location](images/Setupsheet&#32;Open&#32;GUI.jpg)

This will open the setupsheet creation and editing interface. Rename your setupsheet as desired then click to add channels.

![Setupsheet Name Channels](images/Setupsheet&#32;Filename&#32;Add.jpg)

Add and configure properties for all channels to be used. Channels can be added or edited later from the same window.

![Setupsheet Channel Properties](images/Setupsheet&#32;Channel&#32;Properties.jpg)

To finish inserting initial values add an outing, add setupsheet values, and Save & Close.

![Setupsheet Outing Values](images/Setupsheet&#32;Outing&#32;Value&#32;Save.jpg)

### Programmatic Creation
Coming Soon

## Using Setupsheet values
For the Setupsheet values to be used in data analysis two conditions must be met.

The setupsheet file name must match the dataset file name. Wildcards can be insterted with asterisks (*). In the screenshots in the Manual Creation section the Setupsheet name is "*Data 1" for the data files which were named "Sample Data 1"

The setupsheet file must contain the outing number to match the dataset outing number. Outing numbers can be manually edited in the Setupsheet GUI by clicking on an ouring number. For a global Setupsheet or to apply Setupsheet values to all non-specified outings set the outing to 0.

### Using Values in Plots and Math
Setupsheet created channels are Virtual Channels with persistence set with the channel properties. These Virtual Channels can be used the same as all other virtual channels in functions, conditions, and plots.

### Changing existing Setupsheets
Setupsheets can be updated by opening the Setupsheet GUI and clicking on values to be changed. Channels and outings can be edited, added, or deleted at any time.

## Example: Programmatic Setupsheet Creation
Coming Soon
