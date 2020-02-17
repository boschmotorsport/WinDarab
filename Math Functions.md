# Math Channels (and Filters)

- [Math Channels (and Filters)](#math-channels-and-filters)
  - [Math Channels](#math-channels)
  - ['Default' Channels](#default-channels)
    - [Defining Default Channels](#defining-default-channels)
    - [Applying Default Channels](#applying-default-channels)
  - [Working with Functions](#working-with-functions)
    - [“As Default Folder“ Button](#as-default-folder-button)
    - [“Sub-Folder“ Option](#sub-folder-option)
    - [“Make Available” Button](#make-available-button)
    - [Report](#report)
  - [Defining a Function](#defining-a-function)
  - [Formula & Computation Tab](#formula--computation-tab)
    - [Selecting a Channel](#selecting-a-channel)
    - [Selecting a Function](#selecting-a-function)
    - [Compute Function](#compute-function)
    - [Computing Example](#computing-example)
    - [Format Tab](#format-tab)
      - [Numerical Format](#numerical-format)
      - [Range of Values](#range-of-values)
  - [Filter Functions](#filter-functions)
    - [Bandpass, Lowpass, Highpass, and Stopband Functions](#bandpass-lowpass-highpass-and-stopband-functions)
    - ['Filter' Function](#filter-function)
    - [BandpassFIR, LowpassFIR and HighpassFIR Functions](#bandpassfir-lowpassfir-and-highpassfir-functions)
  - [Mathematical Expressions](#mathematical-expressions)
    - [Constants](#constants)
    - [Arithmetic Operators](#arithmetic-operators)
    - [Comparisons](#comparisons)
    - [Logical operators](#logical-operators)
    - [General functions](#general-functions)
    - [Math Functions](#math-functions)
    - [Scripting](#scripting)
    - [Trace functions](#trace-functions)
    - [IIR Filter Functions](#iir-filter-functions)
      - [bandpass](#bandpass)
      - [bandpassFIR](#bandpassfir)
      - [lowpass](#lowpass)
      - [lowpassFIR](#lowpassfir)
      - [highpass](#highpass)
      - [highpassFIR](#highpassfir)
      - [stopband](#stopband)
    - [Lookup Function](#lookup-function)
  - [Examples](#examples)
    - [Example with sigma and dt - Integration over time](#example-with-sigma-and-dt---integration-over-time)
    - [Example with delta and dt - Derivation of a channel](#example-with-delta-and-dt---derivation-of-a-channel)
    - [Example with HOLD - Filtering measurement errors](#example-with-hold---filtering-measurement-errors)
    - [Examples with sigma, lapsigma, dt, and delta - Calculating “highspeed”-duration for each lap](#examples-with-sigma-lapsigma-dt-and-delta---calculating-highspeed-duration-for-each-lap)

In WinDarab it is possible to define filters or new channels with the help of math functions.
WinDarab provides functions and filters that will help you to solve a great number of math and analytical problems.

- In a math function it is possible to use 'comment fields' — in addition to recorded channels — to include conditions that are specific to a particular file. Comment fields are included in the channel selection list and marked with “C”.
- Another approach is to use the 'Setupsheet' functionality to define outing dependant constants

## Math Channels

A math channel calculates values based on other channels in a file. Which channels will be used is determined by the user entered expression.

If a math channel has been defined, it will be listed in the channel window. Much like internal channels, math channels can be used (in nearly all instances) as if they were logged data.

- If new a math channel is added, but another math channel with the same name already exists, the existing math channel is replaced by the new one. In case of a manual creation of the new math channel (Extras/Functions/New) a message box appears, informing the user about the duplicated math channel name.

## 'Default' Channels

WinDarab supports special functions that can be applied to any channel

### Defining Default Channels

Default channels are defined just like any other *Math Function*, just substitute **{default}** in your expression for a channel name:

![Define a Default Channel](images/Math&#32;Function&#32;Define&#32;Default&#32;Channel.jpg)

### Applying Default Channels

|Analysis Window| Instructions|
|:---|:---|
|Oscilloscope|Right click on the channel name<br>The bottom section of the context menu contains available default channels|
|Oscilloscope|Use the ribbon: Channel &rarr; Filter &rarr; Filter channel with:<br> see below|
|X vs Y Plot|In the channel selection box, append the name of the default function with a hyphen.<br>The channel name is in **green** the default function is in **yellow**

Oscilloscope, define default function
![Apply default functions](images/Ribbon&#32;-&#32;Default&#32;Function.jpg)

![X Y Plot, Apply Default Function](images/X%20Y%20Plot%20Default%20Function.jpg)

## Working with Functions

Math functions can be saved in a folder in the File Explorer.
In addition to the selected folder and its contents, the lower area of this window shows a summary of the most important information pertaining to a math function.

<p align="center">
<img src="images/Math Function Explorer.jpg">
</p>

### “As Default Folder“ Button

If you start the program WinDarab makes all functions saved to a specified folder available. To specify this folder select it from the directory and click on the “As Default Folder” button.

### “Sub-Folder“ Option

Activating this button makes all formulae contained in the default folder as well as those contained in the sub-folders available.

### “Make Available” Button

If you would like to make a math function available  you will have to do this explicitly.
This button is not active when the math function has already been made available.

### Report

This button enables you to create a report that contains all the settings for a math function. If you press this button, a dialog box for choosing a report template appears.

### Note <!-- omit in toc -->

- WinDarab provides one template for each language it supports.
- If two functions with the same name exist WinDarab will only use the first one.

## Defining a Function

To define a new math function or to modify an existing one, follow these steps:

1. Use __Tools &rarr; Mathematics &rarr; Functions__ to open the “Functions” dialog box.
2. Select the math function you want to edit and click on “Modify”
    - Or “New Function” if you want to create a new function.
3. The dialog box “Edit Function” appears. It contains three tabs in which you can make all entries pertaining to the math formula.
4. Once you have finished making your entries or modifications, click on “Save“ or “Save as”.

### Notes <!-- omit in toc -->

- When a math function is modified, WinDarab immediately function if it is displayed or in use in a window.
- You can also create a new function by right-clicking into the Channels window and select **Math function &rarr; New**. If you right-click on a function in the Channels window, you can chose to edit this function.
- Math formulas and channels with identical name are not allowed. <br>If a user tries to save a math formula but at least one opened file contains a data channel with the same name, WinDarab asks the user to select a different name for the math formula.
- WinDarab shows a message, if a file contains data channels with the same name as already defined math formulas. The data channels are not available until the user changes the name of the math formula and reopens the file.

## Formula & Computation Tab

- Description
  - Enter a brief description that will be displayed in channel selection lists.
- Expression
  - Enter the math expression you want to calculate in this section.
- Data file to validate the math function
  - Select a file containing a list of channel names. This enables you to access the choice of available channels in the __Insert channel__ area.
  - WinDarab will use this to test the syntax of the expression.
- Insert Math Function
  - This is a list of all available operators, filters, and functions

![Math Function Editor](images/Math%20Function%20Window.jpg)

### Selecting a Channel

- **Channel names should always be enclosed in braces**. Alternatively, you can insert a channel in an expression by using the _Insert Channel area_
  - {default} is a wild-card that can be used. See [Default Channels](#default-channels)
- A formula is not limited to a single line. If a formula is too long or complex for one line, you can split it by using multiple lines.

### Selecting a Function

A user can select a math function from the _Insert Math Function_ section

- Information about each function can be found via intellisense or in [Mathematical Expressions](#mathematical-expressions)

### Compute Function

This area is used to determine the sampling rate for calculating a math function.

Depending on the configuration for recording data, data is sampled at varying intervals. As a result, the number of samples per unit of time may vary.

Depending on the meaning of the variables in a math calculation, it may be necessary to vary the sampling rate. This setting determines the quality and speed of processing.

__for every \<x> sample__:

This setting calculates the function independent of the samples that were recorded and which belong to channels included in the formula. Calculations are instead carried out for each \<x>th sample of

- of all referenced channels: calculates every \<x> sample point of all referenced channels
- of the fastest channel: calculates every \<x> sample point of the fastest channel
- of the selected channel: calculates every \<x> sample point of the selected channel
- of the slowest channel: calculates every \<x> sample point of the slowest channel

Note: If WinDarab searches for the fastest channel it ignores standard channels such as **xtime** or **xdist** because they are included in every block and thus would always be the fastest channels. If you would indeed like to make a calculation for these samples, you must select the **'of the selected channel'**.

__Compute function with a period of \<x> ms:__

WinDarab calculates the function at a specified minimum time interval.

- WinDarab is able to perform a calculation only if sample positions are valid. As a result, WinDarab always searches for the sample separated from the previous sample by at least the specified value. It is therefore possible that the intervals vary – but they are always at least as big as the specified value.

### Computing Example

Assume there are two channels (v_wheel_rb and v_wheel_rf) with different sampling rates (100ms and 130ms) and you want to create a math-channel to calculate the average of these channels.

You can create  a math-channel with the expression “({v_wheel_rb} + {v_wheel_rf})/2”.

The Image  below shows the two channels in the upper area and the math-channel with the computing-configurations “every sample from the fastest channel”, “every sample from the slowest channel”, “every 150ms” (from top to bottom in the bottom area).

![Math Function Calculation Rates](images/Math%20Function%20Calculation%20Rates.jpg)

As you can see, the blue math-channel has the same sample-points as the blue channel (fastest).

The red math-channel has the same sample-points as the red channel (slowest).
The green math-channel has its own sample-points that are not in any way linked to the included channels sample-points.

The sample-points  that are not on the channels-points are interpolated by the surrounding sample-points of the channel. As an example, the blue math-channel uses the exact values from the blue channel and interpolates (where the sample-points are not at the same point by a coincident) the red channel.

### Format Tab

All the settings pertaining to the display of a math channel are made in the “Format” tab.

![Math Function Format Tab](images/Math&#32;Function&#32;Format&#32;Tab.jpg)

#### Numerical Format

Make the settings for the numeric display of the channel values. You are able to choose either a “decimal”, “hexadecimal” or “binary” format. If you choose the decimal format, you are able to specify the width of the entry field as well as the number of decimal places.

#### Range of Values

Use this area to set the range of values (from - to) and the unit of measure to be used in the default channel display.

## Filter Functions

For this section, math foundations of filters are required.
WinDarab provides a lot of math filters, such as:

- bandpass
- bandpassFIR
- filter
- lowpass
- lowpassFIR
- highpass
- highpassFIR
- stopband

They can all be found in the function window in the category “filter functions”

![Highlighted Filter Functions](images/Math%20Function%20Filter%20Window%20Highlighted.jpg)

### Bandpass, Lowpass, Highpass, and Stopband Functions

These Functions all have an editor, where you can  insert the parameters for the function.

In the filtertype-list are up to six different filtertypes, that you can chose for your filter. Each of the filters have individual strengths and weaknesses regarding roll-off or phase response

The other lists supply the parameters for the order, the frequency and the sample frequency.

- Keep in mind, that the sample frequency has to be at least twice the filter frequency.

When all parameters are configured, you can go to the expression editor by clicking on Next.

![Filter Function Editor](images/Math&#32;Function&#32;Filter&#32;Editor.jpg)

In this dialog, you have to enter the expression you want to filter. The expression can be as complex as you require.

- It is also possible to define another filter within this expression by calling up the Assistant again.

### 'Filter' Function

Choosing 'Filter' from the filter funtions allows you to define your own coeffiients.

![Filter First](images/Math&#32;Function&#32;Filter&#32;First.jpg)

- The Assistant supports up to 12 sampling points. If your filter requires more sampling points, you have to add these manually to the expression created by the assistant.

### BandpassFIR, LowpassFIR and HighpassFIR Functions

These functions don’t require an assistant. They all require as parameters the order of the filter, the channel to filter and at least one cut-off frequency (bandpass requires two).

All other parameters like the frequency are calculated.

## Mathematical Expressions

The following sections list all operators and functions supported in WinDarab.
WinDarab follows conventional mathematical rules for evaluating expressions.

### Constants

| | |
|---|---|
|e (Eulers’s number)|e = (1/0!) + (1/1!) + (1/2!) + (1/3!) + ... = 2.7182...|
|NoValue|Allows you to 'filter out' data, no Value is returned and creates a discontinuity in the signal|
|HOLD|Returns the value of the latest calculation result.<br>HOLD can be used to eliminate/replace invalid measurement values.<br>the use of HOLD can slow down math function calculation because the function must be recalculated from the beginning of a file.|
|pi|pi = 3.1415…|

### Arithmetic Operators

| | |
|---|---|
|*|Multiplication|
|+|Addition|
|-|Subtraction|
|/|Division|
|^|![power_f], Calculates the result of \<x> raised to the power of \<y>|
|\<X> BitAnd \<y>|Calculate the result of the bitwise AND-combination of \<x> and \<y>|
|\<X> BitOr \<y>|Calculate the result of the bitwise OR-combination of \<x> and \<y>|
|\<X> BitXor \<y>|Calculate the result of the bitwise XOR-combination of \<x> and \<y>|

[power_f]: http://chart.apis.google.com/chart?cht=tx&chl=x^{y}

### Comparisons

|||
|---|---|
|<|Less Than|
|<=|Less Than or Equal to|
|=|Equal to|
|<>|Not equal to|
|>|Greater than|
|>=|Greater than or Equal to|

### Logical operators

|||
|---|---|
|AND|Logical **AND** Operator|
|NOT|Logical **NOT** Operator|
|OR|Logical **OR** Operator|

### General functions

|||
|---|---|
|average(\<Channel>;\<Samples>)|Calculates the average value of a channel for x(n) within the range n-\<Samples> to n+\<Samples>|
|If (\<Condition> ; \<IfTrue> ; \<IfFalse>)|If the first expression is true, the result of the second expression is returned. Otherwise, the result of third expression is returned.|
|IsSegment|Returns 1, if the car is in one of the given racetrack segments, otherwise 0.<br>The segments can be selected by their number or by name|
|Segment(\<Segmentation Name>|Returns the number of the racetrack segment|
|SegmentIndex(\<SegmentName>|Returns the index of the segment in the selected Segmentation |
|TakeAve(\<channel1>;...;\<channeln>)|Returns the average value of all input channels at the current sample|
|TakeMax(\<channel1>;...;\<channeln>)|Returns the max value of all input channels at the current sample|
|TakeMin(\<channel1>;...;\<channeln>)|Returns the min value of all input channels at the current sample|

### Math Functions

|||
|---|---|
|Abs(\<x>)|Returns the positive absolute value of \<x>.|
|arccos(\<x>)|Calculates the radiant angle, the cosine of which equals the parameter \<x>.|
|ArcCosH(\<x>)|Calculates the radiant angle, the hyperbolic cosine of which equals the parameter \<x>.|
|ArcSin(\<x>)|Calculates the radiant angle, the sine of which equals the parameter \<x>.|
|ArcTan(\<x>)|Calculates the radiant angle, the tangent of which equals the parameter \<x>.|
|ArcSinH(\<x>)|Calculates the radiant angle, the hyperbolic sine of which equals the parameter \<x>.|
|ArcTanH(\<x>)|Calculates the radiant angle, the hyperbolic tangent of which equals the parameter \<x>.|
|ceil(\<x>)|Calculates the smallest integer greater than or equal to to \<x>.|
|Cos(\<x>)|Calculates the cosine of the radiant \<x>.|
|CosH(\<x>)|Calculates the hyperbolic cosine of the radiant \<x>.|
|Exp(\<x>)|Calculates the exponential value ![exp_f] |
|floor(\<x>)|Calculates the biggest integer smaller-equal to \<x>.|
|frac(\<x>)|Returns only the decimals from \<x>.|
|HasValue(\<value>)|True if the value is valid and False if the value is 'NoValue'|
|int(\<x>)|Cuts all decimals from \<x>.|
|lb(\<x>)|Calculates the base-2 log of \<x>. <br>![log2_f]|
|lg(\<x>)|Calculates the base-10 log of \<x>.<br>![log10_f]|
|ln(\<x>)|Calculates the natural log of \<x>.<br>![ln_f]|
|round(\<x>)|Rounds \<x> to the nearest integer value.|
|sign(\<x>)|Returns the sign of \<x> (-1 or 1).|
|Sin(\<x>)|Calculates the sinus of the radiant \<x>.|
|SinH(\<x>)|Calculates the hyperbolic sine of the radiant\<x>.|
|sqr(\<x>)|Calculates ![sqr_f].|
|sqrt(\<x>)|Calculates ![sqr_rt_f].|
|Tan(\<x>)|Calculates the tangent of the radiant.|
|TanH(\<x>)|Calculates the hyperbolic tangent of the radiant \<x>.|
|BitInvert(\<x>)|Calculates the bitwise Inversion of \<x>.|
|**Important**|Due to limitations in precision of math results (because WinDarab is using 32-Bit IEEE-float values) there are problems, if the resulting value is too big. E.g. the result of BitInvert(128) is wrong, while the result of BitInvert(255) is correct.<br>The precision problem occurs only, when saving the math result in memory. While evaluation the expression, there won’t be any precision issues.<br>This means that the expression can evaluate a maximum of 32-Bit values, but the final result should be smaller.|

[exp_f]: http://chart.apis.google.com/chart?cht=tx&chl=e^{<x>}
[log2_f]: http://chart.apis.google.com/chart?cht=tx&chl=log_{2}{x}
[log10_f]: http://chart.apis.google.com/chart?cht=tx&chl=log_{10}{x}
[ln_f]: http://chart.apis.google.com/chart?cht=tx&chl=ln{x}
[sqr_f]: http://chart.apis.google.com/chart?cht=tx&chl=x^{2}
[sqr_rt_f]: http://chart.apis.google.com/chart?cht=tx&chl=\sqrt{x}

### Scripting

|||
|---|---|
|:=|Assignment operator for _Local_ or _Var_ variables|
|begin|Keyword to define the start of a _script_ inside a math function|
|end|Keyword to define the end of a _script_ inside a math function|
|Local|Keyword to define a _Local_ variable, which is a variable that resets to 0 at each new timestamp (doesn't retain its previous value)|
|Var|Keyword to define a script variable that remembers its previous value|

### Trace functions

|||
|---|---|
|Ave(\<channel>)|Calculates the average value of a channel over the file|
|DetectEvent([Rising\|Active\|Falling\|Inactive]; \<BeingCondition>;\<MinTrueDuration>;\<BeginDelay>;\<EndCondition>;\<MinFalseDuration>;\<EndDelay>)|Returns a code from the event detected, if after the begin-condition for the given time (in milliseconds) the end-condition isn't found.<br> Without phase: 1: Begin Event (Rising Edge); 2: Inside Event; -1: End of Event(Falling Edge); 0:Outside Event<br>With phase: True(1) or False(0)|
|delta(\<Channel>)|Calculates the difference between Channel(x(n)) and Channel(x(n-1))|
|dn|Calculates the difference Samples(x(n)) and Samples(x(n-1)).|
|ds|Calculates the difference between  xDist(x(n)) and xDist(x(n-1)).
|dt|Calculates the difference between  xTime(x(n)) and xTime(x(n-1)).
|IsLap([OutLap\|RunningLap\|InLap\|FastestLap\|NormalizedLap];...)|Returns true, if the current lap has one of the listed attributes. You can check for multiple attributes in a single call<br>e.g.:<br>IsLap(InLap;OutLap) returns true, if the lap is an _In_ or _Out_ lap.|
|LapAve(\<Channel>)|Calculates the average value for a channel within the current lap|
|LapIndex|Returns the index of a lap, its a continuous counter starting at 1|
|LapMax(\<Channel>)|Calculates the maximum value of a channel within the current lap|
|LapMin(\<Channel>)|Calculates the minimum value of a channel within the current lap.|
|LapNo|Returns the lap number as shown in the _File Explorer_ pane|
|LapSigma(\<Channel>)|Same as Sigma but with a lap change set as the reset condition.|
|LapStdDev(\<channel>)|Calculates the standard deviation for the channel within the current lap.|
|Lookup(\<TableName>;\<param1>;\<param2>;…)|The lookup table is called with the given parameters which specify the dimensional values.|
|Max(\<Channel>)|Calculates the maximum value of a channel.|
|Min(\<Channel>)|Calculates the minimum value of a channel.|
|OutingNo|Returns the outing number shown in the _File Explorer_ Pane|
|SampleRate(\<channel>)|Returns the average sample rate in milliseconds of the channel|
|SegmentAve(\<Channel>)|Calculates the average value for a channel within the current lap|
|SegmentIndex(\<SegmentName>|Returns the index of the segment in the selected Segmentation |
|SegmentMax(\<Channel>)|Calculates the maximum value of a channel within the current lap|
|SegmentMin(\<Channel>)|Calculates the minimum value of a channel within the current lap.|
|SegmentStdDev(\<channel>)|Calculates the standard deviation of a channel within the current lap.|
|sigma(\<Channel>; \<reset>)|Calculates the sum of Channel(x(0)) to Channel(x(n)). The optional second parameter defines a reset condition that - when occurring - resets the sum and starts from zero again.
|ValueAtDist(\<channel>; \<dist> [; \<LapIndex>])|Returns the value of the channel at the given distance. See [New Math Functions](7.7%20Changes#new-math-functions)|
|ValueAtTime(\<channel>; \<time> [; \<LapIndex>])|Returns the value of the channel at the given time. See [New Math Functions](7.7%20Changes#new-math-functions)|

### IIR Filter Functions

WinDarab provides seven filter functions:

- bandpass
- bandpassFIR
- lowpass
- lowpassFIR
- highpass
- highpassFIR
- stopband

WinDarab supports a number of different approximation techniques and frequencies for each of these filters.

- Tip: Using the WinDarab Filter Assistant simplifies the assembly of filter functions considerably

#### bandpass

Syntax:

- bandpass (\<Technique>;\<Order>;\<Frequency Range>;\<Expression>)

Parameters:
|Technique|Order|Frequency Range>|
|---|---|---|
|Butterworth|1 / 2 / 3 / 4 / 5 / 6 / 7 / 8 / 9 / 10 / 11 / 12|50:100 / 50:200 /100:200 / 150:200|

#### bandpassFIR

Syntax:

- bandpassFIR(\<Order>, \<lowerCutoff>, \<upperCutoff>, \<Channel>)

The channel is filtered using a FIR-bandpass-filter of the given order (>=4th order) and a cutoff frequency [Hz].

#### lowpass

Syntax

- lowpass (\<Technique>;\<Order>;\<Frequency>;\<Expression>)

Parameters:
|Technique|Order|Frequency|
|---|---|---|
|Chebyshev-I|4 / 8 / 10 / 12|5 / 10 / 20 / 50 / 100 / 150 / 200|
|Chebyshev-II|4 / 8 / 10 / 12|5 / 10 / 20 / 50 / 100 / 150 / 200|
|Elliptic|4 / 8 / 10 / 12|5 / 10 / 20 / 50 / 100 / 150 / 200|
|Butterworth|1 / 2 / 3 / 4 / 5 / 6 / 7 / 8 / 9 / 10 / 11 / 12|5 / 10 / 20 / 50 / 100 / 150 / 200|
|FIR-Hamming|40 / 50 / 60|5 / 10 / 20 / 50 / 100|
|FIR-Remez|60|5 / 10 / 20 / 50 / 100|

#### lowpassFIR

Syntax:

- lowpassFIR(Order, CutoffFreq, Channel)

The channel is filtered using a FIR-lowpass-filter of the given order (>=4th order) and cutoff frequency [Hz].

#### highpass

Syntax:

- highpass (\<Technique>;\<Order>;\<Frequency>;\<Expression>)

Parameters:
|Technique|Order|Frequency|
|----|----|----|
|Chebyshev-|4 / 8 / 10 / 12|5 / 10 / 20 / 50 / 100 / 150 / 200|
|Chebyshev-II|4 / 8 / 10 / 12|5 / 10 / 20 / 50 / 100 / 150 / 200|
|Elliptic|4 / 8 / 10 / 12|5 / 10 / 20 / 50 / 100 / 150 / 200|
|Butterworth|1 / 2 / 3 / 4 / 5 / 6 / 7 / 8 / 9 / 10 / 11 / 12|5 / 10 / 20 / 50 / 100 / 150 / 200|
|FIR-Hamming|40 / 50 / 60|5 / 10 / 20 / 50 / 100|

#### highpassFIR

Syntax:

- highpassFIR (\<Order>, \<CutoffFreq>, \<Channel>)

The channel is filtered using a FIR-highpass-filter of the given order (>=4th order) and cutoff frequency [Hz].

#### stopband

Syntax:

- stopband (\<Technique>;\<Order>;\<Frequency Range>;\<Expression>)

Parameters:

|Technique|Order|Frequency Range|
|---|---|---|
|Chebyshev-I|4 / 8 / 10 / 12|50~100 / 50~200 / 100~200 / 150~200
|Chebyshev-II|4 / 8 / 10 / 12|50~100 / 50~200 / 100~200 / 150~200
|Elliptic|4 / 8 / 10 / 12|50~100 / 50~200 / 100~200 / 150~200|
|Butterworth|1 / 2 / 3 / 4 / 5 / 6 / 7 / 8 / 9 / 10 / 11 / 12|50~100 / 50~200 / 100~200 / 150~200|
**The use of the diacritic mark "~" (tilde) between the upper and the lower frequency is mandatory.**

### Lookup Function

Syntax:

- Lookup(\<LookupTable>;\<param1>[;\<param2>…])

Parameters:

- LookupTable: The base table for the lookup-value.
  - For more information on lookup tables see LookupTables.
- param1-x: The input parameters for the first (x) dimension of the lookup table
- param2-y: The input parameters for the second (y) dimension of the lookup table

Note: The number of the dimensional-parameters has to match the dimension of the lookup table.

## Examples

The following examples use a few channels and functions which are:

- speed: The speed of the car in km/h
- lapctr: The current lapnumber
- HOLD: The last value calculated by this math-channel
- dt: Time past since the last calculated sample of this math-channel
- sigma: Sums up the expression inside for the whole file up to the current sample

### Example with sigma and dt - Integration over time

There is no function for integrating a channel over time. No matter, integration over time is simply the sum of a channel multiplied with the delta-time:

In this example the speed is integrated over the file. The result is the distance driven (assuming the unit of speed is km/h, we have to divide by 3.6 to receive the distance in meters)

```
sigma(speed*dt) / 3.6
```

### Example with delta and dt - Derivation of a channel

To derivate a channel by time, you have to divide the change of the channel by the change of time:

```
delta(channel)/dt
```

### Example with HOLD - Filtering measurement errors

Assuming the speed of a car is between 0 and 400 km/h. If we want to clean the speed-channel from all measurement errors (values outside the valid speed-range) we have to find the error values.

```
If (speed <0 OR speed >400;0;speed)
```

Now every wrong value is set to 0. Instead of using this static value, you may want to keep the latest reasonable value. This can be accomplished by inserting the HOLD-function: HOLD returns the previous result of the math channel.

```
If(speed < 0 OR speed > 400; HOLD; speed)
```

### Examples with sigma, lapsigma, dt, and delta - Calculating “highspeed”-duration for each lap

In this example you are shown how to use these functions to generate a math channel that calculates the duration driven with more than 200km/h for each lap.
First thing to do is to sum up the time, the car is faster than 200km/h.

```
sigma(if(speed > 200; dt; 0))
```

The if-function returns the time since the last sample when speed is greater 200 and 0 if not. Sigma sums up the results of the if-function to get the time past driving faster than 200km/h.

Note:

- This current function sums up the time for the whole file.

If you want the time being calculated for each lap individual, you have to reset the sum at the each laptrigger.

Unfortunately the sigma-function works on the whole file by default, so you need to reset the function after each lap. For that matter, the sigma-function has an optional reset condition.

```
Sigma(if(speed > 200; dt; 0); delta(lapctr) <> 0)
```

The new part in this function does exactly that. If the lap number changed (delta(lapctr) <> 0) sigma resets the sum back to zero and starts again.

Note:

- Instead of delta(lapctr) you can also use {laptrig} <> 0.<br>Whatever your choice is, take care of the calculation period of your math channel. Especially {laptrig} is a single peak at the lap trigger and can be easily missed, if the calculation period is set to “Slowest channel”. Therefore using the lap counter is better, but again: If the period is “slowest channel” and your speed is measured faster, you have to select “fastest channel”!<br>For more information see also “Computing Tab”.

There is a faster way to get the same results as well. Use LapSigma for resetting the sum at the beginning of a new lap.

```
LapSigma(if(speed > 200; dt; 0))
```
