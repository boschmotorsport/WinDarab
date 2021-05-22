# Flow Chart

- [Flow Chart](#flow-chart)
	- [Open the Flow Chart Window](#open-the-flow-chart-window)
	- [How Flow Charts Work](#how-flow-charts-work)
		- [The “human” way](#the-human-way)
		- [The 'flow chart' way](#the-flow-chart-way)
	- [Things you should know about Flow Charts](#things-you-should-know-about-flow-charts)
	- [Flow Chart Settings](#flow-chart-settings)
		- [Setup Dialog Box](#setup-dialog-box)
		- [Flowchart Pages](#flowchart-pages)
		- [Output Page](#output-page)
			- [Output Table](#output-table)
			- [Output Value](#output-value)
			- [Output Racetrack](#output-racetrack)
			- [Flow Chart: output can be virtual channels](#flow-chart-output-can-be-virtual-channels)
		- [Design page](#design-page)
			- [Flow objects](#flow-objects)
			- [Variables](#variables)
			- [Start](#start)
			- [Compare](#compare)
			- [Condition](#condition)
			- [Container](#container)
			- [Exit](#exit)
			- [Formula](#formula)
			- [Join](#join)
			- [Next sample](#next-sample)
			- [Range](#range)
			- [Select case](#select-case)
			- [Output to table](#output-to-table)
			- [Output to value](#output-to-value)
			- [Segmentation in Racetrack](#segmentation-in-racetrack)
			- [Links](#links)
		- [Working with the Flowchart Window](#working-with-the-flowchart-window)
			- [Modes](#modes)
			- [Active object](#active-object)
			- [Selected objects](#selected-objects)
			- [Inserting and deleting objects](#inserting-and-deleting-objects)
			- [Move, Copy, Paste Object(s)](#move-copy-paste-objects)
			- [Resize Object](#resize-object)
			- [Object Connectors](#object-connectors)
			- [Connecting objects with links in design pages](#connecting-objects-with-links-in-design-pages)
			- [Editing links](#editing-links)
		- [Executing the Flow](#executing-the-flow)
			- [State of a flow](#state-of-a-flow)
			- [Working](#working)
			- [Iteration](#iteration)
			- [Errors](#errors)
				- [Invalid entry](#invalid-entry)
				- [Endless loop](#endless-loop)
		- [More Examples](#more-examples)
			- [Channel Limit Violation](#channel-limit-violation)
			- [Colorize a Racetrack By Channel Value](#colorize-a-racetrack-by-channel-value)

A Flow Chart is a powerful tool with which you can filter and analyse data. For a rudimentary example you can make left curves as red segments and right curves as blue segments on a racetrack like below.

![Basic Flow Chart](images/Flow&#32;Chart&#32;-&#32;Basic.jpg)

In flow charts you have flow-objects like compare, formula, range, print value in table or value, insert/delete segment in a racetrack and others. The flow-objects have parameters: constants, user defined variables or channels.

The way how WinDarab should analyze the recorded data is described step by step in a flow chart – comparable to a state machine.

In the picture below you can see a part of the flow chart used to create the above example:

![Basic Layout](images/Flow&#32;Chart&#32;-&#32;Sample&#32;Design.jpg)

## Open the Flow Chart Window

To open a Flow Chart Window:

- Select *Windows&rarr;Worksheet controls&rarr; Flow Chart* and drag it into your Workspace.
- Right click on an empty region of the Desktop Analysis Area and select *Flow Chart* from the context menu

## How Flow Charts Work

In this section you’ll get a brief idea how flow charts work – and the way you have to think to analyze data with flow charts successfully.

To illustrate this, we will start with a simple example.

We want to colorize the racetrack with those sections, where the engine revolution is greater than 7000 rpm until it drops below 6500 rpm. The input data should be the current lap (the lap where the cursor is located in).

Here’s an oscilloscope view of the input data (It’s not the whole lap):

![Sample Data](images/Flow&#32;Chart&#32;-&#32;Sample&#32;Data.png)

### The “human” way

Here’s what you would do, if you want to colorize the racetrack with the sections of revolution above 7000 rpm:

1. Start at the first sample of the current lap.
2. Get a blank paper sheet (with the template of the racetrack).
3. Look for the first/next sample with “rev” above 7000 rpm.<br>If the end of lap is reached, the analysis is done!
4. Get the current lap distance “lapdist” and start with colorizing the racetrack.
5. Search for the following sample with “rev” below 6500 rpm.
6. Colorize the racetrack between the start positon (found in 3) and end position (found in 5)
7. Continue to search for all occurrences by repeating step 3-7.
Quite simple, isn’t it ?

### The 'flow chart' way

Now let’s see, how this example is realized as a flow chart analysis.

First, after opening a new flow chart window, you should setup your data source (Settings / F5).<br>
In our example, we want to evaluate the current lap of some file:

![Flow Chart Settings](images/Flow&#32;Chart&#32;-&#32;Settings.jpg)

The next step is to insert a racetrack view object on the output page:

|![Racetrack](images/Flow&#32;Chart&#32;-&#32;Racetrack.png)|![Racetrack Settings](images/Flow&#32;Chart&#32;-&#32;Racetrack&#32;settings.png) |
|---|---|

And the last step is to create the flow chart, which looks like this – actually exactly the same as described in the “human” way.

![Sample Flow Chart](images/Flow&#32;Chart&#32;-&#32;Sample&#32;Flow.png)

||||
|---|---|---|
|1|![Start Icon](images/Flow&#32;Chart&#32;-&#32;Start&#32;Icon.png)|START is the entry point of the flow chart analysis.|
|2|![Red Segment](images/Flow&#32;Chart&#32;-&#32;Red&#32;Segment.png)|This “racetrack” object clears the current racetrack segmentation (which is located on the output tab)|
|3|![Example Compare](images/Flow&#32;Chart&#32;-&#32;Example&#32;Compare.png)|The condition node “rev >= 7000” instructs the flow chart to look for the next sample where the condition get true.|
|4|![Example High Rev](images/Flow&#32;Chart&#32;-&#32;Example&#32;High&#32;Rev&#32;Segmentation.png)|The racetrack object inserts a segment change (start of segment “Red” – “high rev”).|
|5|![Example Compare Setup](images/Flow&#32;Chart&#32;-&#32;Example&#32;Compare&#32;Block.png)|The condition node “rev < 6500” instructs the flow chart to look for the following sample, where the revolution drops below 6500 rpm.|
|6|![Exaple Green Segment](images/Flow&#32;Chart&#32;-&#32;Example&#32;Green&#32;Segment.png)|Now the next racetrack objects inserts the next segment change (start of segment “Green” – “rev normal”) and go back to step 3.|

You don’t have to mention in a flow chart when to stop the analysis **(but you can in special cases!)**. A flow chart will always stop at the end of the selected data range (or never, if using with telemetry data)
After running the flow chart (by disabling the “design” mode), you can see the analysis result in the output window:
![Example Ouput](images/Flow&#32;Chart&#32;-&#32;Example&#32;Segment&#32;Output.png)

## Things you should know about Flow Charts

|||
|---|---|
|![Possible Transitions](images/Flow&#32;Chart&#32;-&#32;Possible&#32;Transitions.png)|A flow chart is a combination of state machine and its evaluation rules.<br>In a state machine “nodes” represent the states and the “links” or ”lines” describe the possible transitions between the states.<br>In flow chart the “exit” of a node (which was passed last) represents the current state and the nodes linked to the exit are the possible transitions for continuation.|
|![Flow](images/Flow&#32;Chart&#32;-&#32;Calculation&#32;Flow.png)|The flow chart will move forward in the data until:<br>- a node connected to the current state (exit) evaluates to one of its exits or<br>- the end of the data evaluation range is reached.<br>Normally you don’t have to care about proceeding the walk through the data.<br>In the left example you can see, that it’s not required to connect the false exit of the condition with its entry. In real this would be worse: **See next example**!|
|![Checking Multiple Connections](images/Flow&#32;Chart&#32;-&#32;Multiple&#32;Links.png)|**Correct Usage:**<br>In case you want to test for alternatives create multiple links between the exit of a node and the entries of multiple nodes:<br>Flow Chart will check both “rev <= 4000” and “rev >= 7000”. As long as both are “false”, Flow Chart will move forward in the data. If one evaluates to “true”, Flow Chart will transit the current state to the corresponding “true” exit.|
|![Incorrect Multiple Connections](images/Flow&#32;Chart&#32;-&#32;Incorrect&#32;Multiple&#32;Links.png)|**Incorrect Usage:**<br>This is not correct for checking alternative routes: If “rev <= 4000” is false, the flow chart will transit to the “false” exit of “rev <= 4000”:<br>Flow Chart will wait for “rev >= 7000” and won’t check “rev <= 4000” anymore!|
|![Multiple Connections at the same time](images/Flow&#32;Chart&#32;-&#32;Multiple&#32;Links&#32;Concurrently.png)|If you want to check for two conditions to be true at the same time, you have to take care to proceed walking through the data.<br>Omitting the “NEXT SAMPLE” object in the left example a short circuit would be the result. The flow chart will stuck at the first sample where “rev >= 7000” is true and “speed >= 250” is false!|
|![Better Performance](images/Flow&#32;Chart&#32;-&#32;Better&#32;Multiple&#32;Links&#32;Concurrently.png)|A better performance can be reached, if you find a flow chart solution without using “NEXT SAMPLE”.<br>The example above was changed to test “rev >= 7000” again after “speed >= 250” got true.<br>If “rev >= 7000” isn’t true any more, you can return to the begin of the sequence - and “NEXT SAMPLE” is not required anymore.<br>This is more performant, but less readable. Use at your discretion|
|![More Readable](images/Flow&#32;Chart&#32;-&#32;Readable&#32;Multiple&#32;Links.png)|The more conditions you have which should be “true” at the same time, the more complex this check will be.<br>It may be resonable to place the condition check into a container. It makes the main flow more readable !|
|![Multiple Container Exits](images/Flow&#32;Chart&#32;-&#32;Containers&#32;Multiple&#32;Exits.png)|Note: A container can provide any (reasonable) number of “EXIT” objects.|
|![Internal State](images/Flow&#32;Chart&#32;-&#32;Internal&#32;State.png)|A container has its own internal state. This means the outer flow chart state won’t transit inside of the container. The outer state will only transit to the exit of a container, if the container flow inside reaches an “EXIT” object (on the left the “True” node).<br>Use parallel containers if you need a complex logic to decide on which path the evaluation has to continue.|
|![Multiple Main Tabs](images/Flow&#32;Chart&#32;-&#32;Multiple&#32;Main.png)|Use multiple “main” flow chart tabs, if you create multiple indepentent flow charts, which use the single output tab for their results.<br>Note: You can use containers also but they aren’t designed for this pupose!|
|![Alternative State](images/Flow&#32;Chart&#32;-&#32;Alternative&#32;State.png)|In case you want to test for alternatives create multiple links between the exit of a node and the entries of multiple nodes:<br>- Flow Chart will check both “rev <= 4000” and “rev >= 7000”. As long as both are “false”, the Flow Chart will move forward in the data.<br>- If one evaluates to “true”, Flow Chart will transit the current state to the corresponding “true” exit.|
|![Incorrect Alternative State](images/Flow&#32;Chart&#32;-&#32;Alternative&#32;State&#32;Incorrect.png)|This is not correct for checking alternative routes: If “rev <= 4000” is false, the flow chart will transit to the “false” exit of “rev <= 4000”:<br>The Flow Chart will wait for “rev >= 7000” and won’t check “rev <= 4000” anymore!|
|![Flow Chart Variables](images/Flow&#32;Chart&#32;-&#32;Variables.png)|It’s a good practise to use variables to store information and to separate (a little bit) between output objects and analysis logic.<br>This can be helpful to organize the flow chart but also to be able to add additional logic (e.g. logic to supress events because of their duration).|

## Flow Chart Settings

A dialog box with settings appears automatically when you open the Flowchart Window for the first time. Closing the window will save the settings. The next time the window is opened the dialog will not appear instead the saved settings will be loaded.

If you want to modify settings or carry out a new calculation, you can re-open the dialog box:

- Using the menu item **“Start&rarr; Settings&rarr; Edit”**
- Using the context menu by pressing the middle mouse button
- Using the context menu by pressing the left + right mouse buttons.
- Using the hotkey, **F5**

Flow Chart has flow-objects and most of them have parameters and **Setup Dialogs**. If there is an active flow-object \[red frame\] then using any of the above to open Settings will open its Setup dialog.

You can **Load** and **Save** settings with the **F6** and **F7** Hotkeys, respectively.

### Setup Dialog Box

This dialog box is similar to Common Overlays Settings, but because only one overlay is used instead of a table with overlays there is a list box to choose only one overlay. There is also a additional edit box to change the name of current page of the flow register.

![Flow Chart Settings](images/Flow&#32;Chart&#32;-&#32;Settings.jpg)

### Flowchart Pages

There is one output page where the calculation results are shown and at least one design page(s). A Design page can represent a flowchart or a container. During editing you can:
|||
|---|---|
|Start&rarr; Flow Pages&rarr; New flow|add a new Design Page|
|Start&rarr; Flow Pages&rarr; Delete flow|delete current Design Page.|
|Start&rarr; Flow Pages&rarr; Close container|If the Design Page represent a container then you cannot delete it, but you can close it. Closing means the objects from Design Page become invisible.|

### Output Page

This page contains analyzed or filtered results, calculated during flows run. The result can be a simple value, multiple values organized as a table, virtual channels from table columns, or segments in a racetrack.

#### Output Table

|||
|---|---|
|Insert/Table|During calculations you can print different values in cells of the Output table.|
|Context Menu/ Settings -Or- F5|If the object is active (with red frame), you can open and modify its settings. You can open the “Output Table” dialog box using the context menu by pressing right mouse button.<br>![Output Table](images/Flow&#32;Chart&#32;-&#32;Output&#32;Table.jpg)
||A row in the Column Definition Table contains the Name and the Type of the column. If the column is a number then you also can choose the length and the decimals of the number. You can change the order of columns with Up / Down arrows.|
|Columns as Virtual Channels|Virtual channels can be created from columns in the output table, check the 'VirtChannel' box. These virtual channels can be made persistant (meaning they save to the file), check the 'Persist' box. You can then set the unit, minimum view range, and maximum view range.|
|Add Column|A new row is added if you enter a name into the last empty row.|
|![Delete Button](images/Delete&#32;Button.png)|If you want to delete a row then make the row current and then press the delete button.|
|Zoom range in measure window|If you want to be able to double click on the output table and zoom an oscilloscope, define two columns \(**Start** and **End**\)|
|Go to position in measure window|If you only define a **Start**, set the radio button to 'Go to position in measure window' and when you double-click the row in the output table only the cursor will move.|
|Sorting|You can sort the results of the table by a clicking on the column heading of the table. By default after calculations the results are sorted by the column chosen in the field Start (In our example it is Time column). If you click on other column results will be resorted and the new sort column will be remembered and after next calculations will be used to sort the results. If there are several results with the same value for current sort column then they will be sorted by the values of column in Start field.|
|Maximum Rows|The table cannot contain more than 10000 rows. If there are already 10000 rows, the new rows will be ignored.|

#### Output Value

|||
|---|---|
|Insert/Value|During calculations you can print a value in Output Value, and after the calculation you can analyze it.|
|Context Menu&rarr; Settings<br>F5<br>Double Click|If the active object has a red frame, you can open and modify its settings.|
||If you select the check box “Value is a time value” this means that the printed value is a time and with double clicking on it the bounded Oscilloscope will go on this time position.|

#### Output Racetrack

|||
|---|---|
|Insert/Racetrack|During calculations you can insert segment, delete segments or delete all segments in an Output Racetrack.<br>![Example Segmentation](images/Flow&#32;Chart&#32;-&#32;Example&#32;Segment&#32;Output.png)|
|Local Menu&rarr; Settings<br>F5|If, the object is active (with red frame), you can open and modify its settings. You can open the dialog box using the context menu with pressing right mouse button.|

#### Flow Chart: output can be virtual channels

- Columns in any output table can be enabled to create/populate a virtual channel. The virtual channel can be used in any other view of WinDarab for futher analysis.
- Peristent channels are also supported for single files (not linked files and not telemetry), but only if the evaluation “Whole file” is selected for the flow chart.
Note: Be aware that persistent channels are replaced each time the flow is executed!
- The name of the column is used as the name of the virtual channel and the name of the table is used as the data source.
Nevertheless to prevent name conflicts we encourage the use of „unique names“. WinDarab will resolve channel name conflicts**  nevertheless depending on the execution order of Flow Charts the name conflicts aren’t always resolved the same way!

Setup of the Output Table:

<p align="center">
<img src="images/Flow Chart - Virtual Channel Setup.jpg">
</p>

Example Flow chart (calculate the average engine rpm (nmot) above 6000 rpm):

<p align="center">
<img src="images/Flow Chart - Flow.jpg">
</p>

Example Output (oscilloscope and XY Plot):
<p align="center">
<img src="images/Flow Chart - Virtual Channel Visualisation.jpg">
</p>


### Design page

#### Flow objects

There are compare, condition, container, exit, formula, join, next sample, range select case, print in table, print in value and segmentation in racetrack.
<br>
<p align="center">
<img src="images/Flow Chart - Flow Objects.jpg">
</p>

#### Variables

You need variables to store values, for example the flow-object formula needs variable to store the calculated result.
|||
|:---:|:---|
|Variables<br>![Variable Icon](images/Flow&#32;Chart&#32;-&#32;Variable&#32;Icon.png)|From most setups of flow object it is possible to open the table with all user defined variables.<br>![Variable Setup](imsages/../images/Flow&#32;Chart&#32;-&#32;Variable&#32;Setup.jpg)<br>A table row contains a variable and its value.<br>A new row is added if you make the last empty row current and write variable name. A new empty row will be added after insertion.|
|Delete<br>![Delete Button](images/Delete&#32;Button.png)|If you want to delete a row then make the row current and then press the delete button.<br>Parameters<br>While working with flow-object you can use constant-numbers (1, 2, 5.6 …), constant-strings (“This is a string”), channels and variables. We will call parameter any of these objects.|

#### Start

It is used as a start object of a flow. It has no settings. You cannot insert or delete it.

![Start Icon](images/Flow&#32;Chart&#32;-&#32;Start&#32;Icon.png)

#### Compare

|||
|:---:|---|
|Insert/Compare<br>![Compare Icon](images/Flow&#32;Chart&#32;-&#32;Compare&#32;Icon.png)|It is used to compare 2 parameters.<br>The red arrow means the comparison is false; the green one means it is true.<br>Tip: If you move the mouse cursor over them a small window appears with their meaning.|
|Settings - F5|If the object is active (with red frame), you can open and modify its settings. You can open the dialog box using the context menu with pressing right mouse button.<br>![Settings](imsage/../images/Flow&#32;Chart&#32;-&#32;Compare&#32;Settings.jpg)|

#### Condition

|||
|:---:|---|
|Insert&rarr;Condition<br>![Condition](images/Flow&#32;Chart&#32;-&#32;Condition&#32;Icon.png)|You can use any earlier created condition.<br>The red arrow means the condition is false<br>The green arrow one means the condition is true.|
|Tip:|If you move the mouse cursor over them a small window appears with their meaning.|
|Settings - F5|If the object is active (with red frame), you can open and modify its settings. You can open the dialog box using the context menu with pressing right mouse button.<br>![Condition Settings](images/Flow&#32;Chart&#32;-&#32;Condition&#32;Settings.jpg)<br>You can build the condition using a dialog with the available functions and a dialog with the available channels (buttons Function… and Channel…).|

#### Container

|||
|:---:|---|
|Insert&rarr;Container![Container Icon](images/Flow&#32;Chart&#32;-&#32;Container&#32;Icon.png)|If you want to use a block of objects several times you can create a container and then use it as a single object.|
|Settings - F5|If the object is active (with red frame), you can open and modify its settings. You can open the dialog box using the context menu with pressing right mouse button.<br>![Container Settings](images/Flow&#32;Chart&#32;-&#32;Container&#32;Settings.jpg)|
|Tip:|Double clicking on the container will open a new page with the content of the container. To open setup of the container press F5 or use the context menu|

An example of a container:

![Container Example](images/Flow&#32;Chart&#32;-&#32;Container&#32;Example.png)

Where _Speed is bigger_ and _Speed is smaller_ are exits of the container.
See also: [Exit](#exit).

Tip:

The green arrows of the container are the exits, if you move the mouse cursor over them a small window appears with the name of the exit.

#### Exit

|||
|:---:|---|
|Insert&rarr;Exit<br>![Exit Icon](images/Flow&#32;Chart&#32;-&#32;Exit&#32;Icon.png)|It is used to exit the current container and return to its parent.<br>See also: [Container](#container).|
|Settings - F5|If the object is active (with red frame), you can open and modify its settings. You can open the dialog box using the context menu with pressing right mouse button.|
|Tip|Double clicking on the container will open a new page with the content of the container. To open setup of the container press F5 or use the menu|

#### Formula

|||
|:---:|---|
|Insert/Formula|You can calculate a formula for the current sample like mathematical functions; the result is remembered into a variable.<br>See also: [Math Functions](Math%20Functions) and [Container](#container)|
|Settings - F5|If the object is active (with red frame), you can open and modify its settings. You can open the dialog box using the context menu with pressing right mouse button.<br>![Formula Settings](images/Flow&#32;Chart&#32;-&#32;Formula&#32;Settings.jpg)|
|Tip|You can calculate the Ave, Min, Max, Sum of a formula for every sample in a range by selecting Ave, Min, Max or Sum  from "Calculate formula for:". The range is between two parameters ("from", "to").|
||You can build the formula using a dialog with the available functions and a dialog with the available channels (buttons **Function** and **Channel**). See also: [Defining a Function](Math%20Functions#defining-a-function).|

#### Join

|||
|:---:|---|
|Insert&rarr;Join<br>![Join Icon](images/Join&#32;Icon.png)|Join has no settings. It is used to collect several links and from it can start several links too.<br>![Join](images/Flow&#32;Chart&#32;-&#32;Join&#32;Block.png)|

#### Next sample

|||
|:---:|---|
|Insert&rarr;Next sample<br>![Next Icon](images/Flow&#32;Chart&#32;-&#32;Next&#32;Icon.png)|Next sample has no settings. It will increase the current sample.<br>![Next Sample](images/Flow&#32;Chart&#32;-&#32;Next&#32;Sample.png)|

#### Range

|||
|:---:|---|
|Insert&rarr;Range![Range Icon](images/Flow&#32;Chart&#32;-&#32;Range&#32;Icon.png)|Range is used to check if a parameter is between two limits. A limit can be constant or a variable.<br>![Range](images/Flow&#32;Chart&#32;-&#32;Range.png)<br>The red arrow means out of range, the green one means it is inside.|
Tip|If you move the mouse cursor over the arrows a small info window appears.|
|Settings - F5|If the object is active (with red frame), you can open and modify its settings. You can open the dialog box using the context menu by pressing right mouse button.<br>![Range Settings](images/Flow&#32;Chart&#32;-&#32;Range&#32;Settings.jpg)|

#### Select case

|||
|:---:|---|
|Insert&rarr;Select case<br>![Select Case Icon](images/Flow&#32;Chart&#32;-&#32;Case&#32;Icon.png)|The select case allows selection among multiple comparisons, depending on the select parameter.<br>![Select Case](images/Flow&#32;Chart&#32;-&#32;Select&#32;Case.png)|
|Settings - F5|If the object is active (with red frame), you can open and modify its settings. You can open the dialog box using the context menu with pressing right mouse button.<br>![Select Case Settings](images/Flow&#32;Chart&#32;-&#32;Select&#32;Case&#32;Settings.jpg)|
|Tip|A table row contains a case.  You can change the order of cases with Up / Down arrows.|
||Checking of cases starts from the first one and continues down until a comparison evaluates to **True**.|
||A new row is added if you click the last empty row and select an operator or enter a value. A new empty row will be added after insertion.|
|Delete<br>![Delete Icon](images/Delete&#32;Button.png)|If you want to delete a row then select the desired row and press the delete button.|

#### Output to table

|||
|:---:|---|
|Insert&rarr;Output to table<br>![Output To Table Icon](images/Flow&#32;Chart&#32;-&#32;Output&#32;To&#32;Table&#32;Icon.png)|Use Print in table to define in which Output Table and which cell of the table you want to print. The Print in table has the name of its Output Table.<br>![Output To Table](images/Flow&#32;Chart&#32;-&#32;Output&#32;To&#32;Table.png)
|Settings - F5|If the object is active (with red frame), you can open and modify its settings. You can open the dialog box using the context menu with pressing right mouse button.<br>![Output to Table Settings](images/Flow&#32;Chart&#32;-&#32;Output&#32;To&#32;Table&#32;Settings.jpg)<br>A setup-table row contains a column from Output table and the value you want to print there. You can change the order of rows with Up / Down arrows.<br>A new row is added if you select the last empty row and then select a column name and parameter. A new empty row will be added after insertion.|
|Output Row|"Output row" is used to find the row in which to print. If "New row" is checked then a new row is inserted into the Output Table. If you want you can save the row in some variable for later use.<br>If you check "Existing row" the row is the value from a variable specified below. See also: [Output Table](#output-table).|

#### Output to value

|||
|:---:|---|
|Insert&rarr;Output value<br>![Output Value Icon](images/Flow&#32;Chart&#32;-&#32;Output&#32;Value&#32;Icon.png)|Use Output value to define in which Output tab value you want to print. The Output value has the name of its Output page value.<br>![Output Value](images/Flow&#32;Chart&#32;-&#32;Output&#32;Value.png)<br>See also: [Output Value](#output-value).|
|Settings - F5|If the object is active (with red frame), you can open and modify its settings. You can open the dialog box using the context menu with pressing right mouse button.<br>![Output Value Settings](images/Flow&#32;Chart&#32;-&#32;Output&#32;Value&#32;Settings.jpg)|

#### Segmentation in Racetrack

|||
|:---:|---|
|Insert/Segmentation in racetrack<br>![Segmentation in Racetrack Icon](images/Flow&#32;Chart&#32;-&#32;Segmentation&#32;in&#32;Racetrack&#32;Icon.png)|Use Segmentation in racetrack to define which Output Racetrack you want to modify. The Segmentation in racetrack has the name of its Output Racetrack.<br>![Segmentation in Racetrack](images/Flow&#32;Chart&#32;-&#32;Segmentation&#32;in&#32;Racetrack.png)|
|Settings - F5|If the object is active (with red frame), you can open and modify its settings. You can open the dialog box using the context menu with pressing right mouse button.<br>![Segmentation in Racetrack Settings](images/Flow&#32;Chart&#32;-&#32;Segmentation&#32;in&#32;Racetrack&#32;Settings.jpg)|
You can select action:

- Clear all segments (Insert segment will not be available) 
- Insert a new segment with a specified color. The inserted segment can be at 
  - current lap position (current sample).
  - any value saved in a variable.

See also: [Output Racetrack](#output-racetrack).

#### Links

The objects in design pages are connected with links.

![Links](images/Flow&#32;Chart&#32;-&#32;Links.png)

See also: Connecting objects with links in design pages.

### Working with the Flowchart Window

#### Modes

There are two modes: **Edit** and **Auto Run**, for the flow window.

|Edit mode||
|:---|---|
|Start&rarr;Settings&rarr;Design<br>![Edit Mode Icon](images/Flow&#32;Chart&#32;-&#32;Edit&#32;Mode&#32;Icon.png)|In edit mode you can insert, delete, copy, paste objects or links.|

|Run mode||
|:---|---|
|Start&rarr;Tools&rarr;Replay<br>![Replay Icon](images/Replay&#32;Icon.png)|_Run mode_ will switch _edit mode_ off. All flows will then be executed; one after another using the order of pages|
In this mode there are several cases in which calculation will start again automatically:

- The sample range has changed (moving in bounded measure window, online files).
- Settings have changed (after OK of setup dialog or after loading).

In _Run mode_ you can move, rearrange objects and change links, but it is not allowed to make changes in the logic of the flow.

"Edit mode" will stop current execution (see also Executing the flows) and "Run mode" will be switched off. This means that you will not have any updated results in output objects until you switch on "Run mode" mode again.

#### Active object

Clicking on an object will make it active. The active object has a red frame.

You can open and modify the active object settings. Open the dialog box using the context menu by pressing the right mouse button or using the hotkey **F5**.

- Only one object can be active at one time but you can mark several objects.

#### Selected objects

Hold **Ctrl** and click on objects you want to mark. The last clicked object will be also active object. You can mark objects also by dragging a rectangle on the page with left mouse button. All objects that are inside the rectangle will be selected.

The selected objects have a blue frame.

If two objects from a design page are selected then the links between them are also highlighted.

#### Inserting and deleting objects

Flow objects - Design page

|Insert||
|:---|---|
|![Flow Objects](images/Flow&#32;Chart&#32;-&#32;Flow&#32;Objects.jpg)|You can insert an object in Output or Design page using the menu Start&rarr;Flow objects.<br>Drag an Item into your Flow chart to use it.|
|![Flow Object Context Menu](images/Flow&#32;Chart&#32;-&#32;Flow&#32;Object&#32;Context.png)|The context menu is opened with the right mouse click. From the menu select the **Insert** and then select an object.|

- **Insert is only available in edit mode.**

|Delete||
|:---|---|
|![Flow Chart Context Menu](images/Flow&#32;Chart&#32;-&#32;Context&#32;Menu.png)|Delete marked objects<br>The marked objects (all with blue frame) will be deleted. The links between marked objects will be deleted too.|

If you press a button with a flow object on the toolbar you enter the _insert mode_ for the object. In _insert mode_ every click on the page will be inserting an object only if the click is not associated with other actions with bigger priority (move, resize, connect-click on connectors of an object).

|Switch off insert object mode||
|:---|---|
|![Edit Mode Icon](images/Flow&#32;Chart&#32;-&#32;Edit&#32;Mode&#32;Icon.png)|Press the arrow on the toolbar to switch off the insert mode.|

#### Move, Copy, Paste Object(s)

|||
|:---|---|
|![Flow Chart Context Menu](images/Flow&#32;Chart&#32;-&#32;Context&#32;Menu.png)|If there are marked objects you can move them. Moving one of the marked objects will move all others too. The relative arrangement between them will stay. Only the links which connect marked object with not marked one will be changed during the movement. You can use the keys Up, Down, Right, Left to move the selected objects also.|
|Copy|Will copy all marked objects (and their links if any) to clipboard.|
|Paste|If clipboard is not empty you can paste the objects (and their links if any) from the clipboard.<br>You cannot paste output objects to design page and vice versa, but you can copy objects from one design page and then paste them in another design page.|

#### Resize Object

If only a part of the name of an object is visible you can resize the object for the best fit. First make the object active and then if the mouse is near the frame of the object, you will see the resize mouse cursor and then you can resize it.

#### Object Connectors

|![Range](images/Flow&#32;Chart&#32;-&#32;Range.png)|Every object in design pages has one input and/or one or several outputs. They are used to define the direction of execution. The object "Start" has no input connector.|
|:---|---|
|Input Connector|If the link which enters the connector is active then the object will start working.|
|Output Connector (True Condition)|If this output is found as the results of the calculation of an object then the link which starts from with will be activated. In compare, condition and range this connector is chosen if the result is true.|
|Out-Connector (False Condition)|In compare, condition and range this connector is chosen if the result is false.|

#### Connecting objects with links in design pages

You can connect objects with links. A link is created if you drag from output connector to input connector (or vice versa) with left mouse button down. The line will follow the mouse cursor.

If the mouse cursor is over a connector it gets lighter. You can start a link when it is in edit mode and the connector is lighter color. You can finish the link if the end connector is lighter.

**Tip:** If the mouse cursor is over an output connector and you press right mouse button (content menu will appear) and select an object from "Insert" item of the content menu then the input connector of inserted object will be connected with the output connector.

#### Editing links

Clicking on a link will make it active. Then you can change the link with moving some parts (sub lines) of it left, right, top or bottom.

![Links](images/Flow&#32;Chart&#32;-&#32;Links.png)

### Executing the Flow

#### State of a flow

The state of the flow is defined by current sample and working object or active link.

#### Working

In any time of execution there is only one working object or active link. The working object can use the current sample with some channel and/or information saved in variables and can save result in a variable or print it in output object. Depending on the result the working object will select an active link. The task of active link is to select next working object and so on.

**Important:** If the working object cannot select a new active link then the current sample will be increased automatically and the last active link will be activated.

For example you have a compare object with an input link, output link if comparison is true and no link if the comparison is false.

![Example](images/Flow&#32;Chart&#32;-&#32;Max&#32;Value&#32;Example.png)

Then the input link will make the object work and suppose that for the current sample the **MaxValue >= speed** (i.e. False). Then, since there is no link to the False connector, the current sample will be incremented and the input link will be evaluated again. The result of this is: the output link will be reached when a sample for which the speed is bigger as the MaxValue appears.

The equivalent scheme is

![Example](images/Flow&#32;Chart&#32;-&#32;Max&#32;Value&#32;Example&#32;Equivalent.png)

**Important:** You should be careful when using no link feature. If it is used wrong then unexpected results are possible.

#### Iteration

The execution of a flow for a single sample is an iteration. You can go to the next iteration by using a "NEXT" object. See also: [Next Sample](#next-sample).

**Important:** Because the calculations can take much time especially if the range is about the whole file, they are made inside of a working thread. Pause and Stop button are enabled. Instead of waiting for them you are free to work with some other analysis windows.

**Important:**For online[Telmetry] files, calculations are started automatically after a new samples have been received.

#### Errors

##### Invalid entry

Before running a flow the application prepares some elements of the flow. For example locking used channels. If there is an element which cannot be prepared from the application (for example channel name which is not in current file) then a message appears and the setup of the element will be opened and the wrong parameter will have a light red background. The calculation will not start.

##### Endless loop

During execution of a flow the application checks if there is a progress of execution. Usually if the flow stays more than some time executing one sample then it is supposed that there is an endless loop and the calculation will stop. The supposed endless loop will be shown to the user.

![Endless Loop](images/Flow&#32;Chart&#32;-&#32;Endless&#32;Loop.png)

### More Examples

#### Channel Limit Violation

The following flowchart can be used to check a channel for limit violations. Every limit violation is reported to a data table on the output tab containing the channel name, timestamps, duration and the min/max value.

![Channel Limit Violation](images/Flow%20Chart%20-%20Channel%20Limit%20Violation.png)

The upper and lower limit for the limit violation check is initialized at the beginning of the flowchart and can be easily modified.
The output table is designed to show violations of multiple channels. You can copy and modify the flowchart for each channel you want to observe - but you have to replace the channel in several objects.

**Note:** _ValueMin_ is calculated as the minimum value of “rev” in the time range _xTimeStart_ to _xTimeEnd_

Here’s the result table of two flowchart evaluationg “rev” and “accy”.

![Channel Limit Violation Output](images/Flow&#32;Chart&#32;-&#32;Channel&#32;Limit&#32;Violation&#32;Output.png)

#### Colorize a Racetrack By Channel Value

This flowchart uses a “Select Case” object to categorize the current speed into zones and creates appropriate segments for a racetrack element on the output tab.

![Colorize Racetrack By Channel Value](images/Flow&#32;Chart&#32;-&#32;Color&#32;Racetrack&#32;By&#32;Value&#32;Example.png)

If  a zone is entered, the racetrack segment is created and two variables are set with the limits of the zone (2 km/h are added to avoid jitter). As soon as the current speed goes outside of the limits the loop begins for new.
Here’s the result of the flow calculated for the current lap:

![Colorize Racetrack By Channel Value Output](images/Flow&#32;Chart&#32;-&#32;Color&#32;Racetrack&#32;By&#32;Value&#32;Example&#32;Ouput.png)