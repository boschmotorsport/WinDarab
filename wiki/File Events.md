# File Events

- [File Events](#file-events)
  - [Description](#description)
  - [Creation](#creation)
    - [Racecon](#racecon)
    - [Event Rules Window](#event-rules-window)
    - [Rule Dialog](#rule-dialog)
  - [Tutorial](#tutorial)

## Description

File Events are 'Points of Interest' in a datafile.

![File Event](images/Oscilloscope%20-%20File%20Event.jpg)



## Creation

File Events can be definied in two places:

1. In the Racecon project (depending on the logger firmware)
2. In the 'Event Rules' Window

### Racecon

Configuration of File Events in Racecon is outside the scope of this manual

### Event Rules Window

File Events are defined in the 'Event Rules' window (pictured below)

![Event Rules Overview Window](images/Event%20Rules%20-%20Overview.png)

This window gives an overview over:

- File Event Groups
- File Event Rules
  - The total number of events per Overlay
  - The Windows Username of the creator
  - The PC name of the creator
  - A user defined description of the rule

### Rule Dialog

![Define Rule](images/File%20Event%20-%20Tutorial%20define%20rule.png)

- Category
  - Select (or Create) a category to hold your rules
  - Usually something like 'Gearbox' or 'Traction Control'
- Selecting a channel
  - Pick the channel that you want to define the rule for
  - Something like *nmot*
- Define the begin and end conditions
  - Something like:
    - Begin condition > 8000 for 100 ms
    - End condition < 7500 for 10 ms
    - If nmot goes about 8000 rpm for 100ms, the event starts and stays active until nmot goes back below 7500 rpm for 10 ms
- Blink/Alert channel in oscilloscope
  - While the event is true, the channel will blink in an oscilloscope
- Save found occurences in file
  - If a data engineer has a lot of events and wants to share these with others, checking this box will write the events into datafiles when they are loaded.

## Tutorial

|||
|---|---|
|Open the *Events rules* window|![Event Rules](images/File%20Event%20-%20Tutorial%20event%20rules%20window.png)|
|Create a new category<br>- Name the category<br>- Select a color |![New Category](images/File%20Event%20-%20Tutorial%20new%20category.png)|
|Create a new rule|![New Rule](images/File%20Event%20-%20Tutorial%20new%20rule.png)|
|Define the rule|![Define Rule](images/File%20Event%20-%20Tutorial%20define%20rule.png)|
