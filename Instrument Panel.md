# Instrument Panel

The *Instrument Panel* is a window used to visualize data at the current cursor position.

## Settings

Instrument Panel settings can be edited/loaded/saved using the **F5/F6/F7** function keys (like many other windows)

## Elements

The elements that can be used on an *Instrument Panel* are:

- [Instrument Panel](#instrument-panel)
  - [Settings](#settings)
  - [Elements](#elements)
    - [Value Display](#value-display)
      - [Value Display Common Settings](#value-display-common-settings)
      - [Value Display Alert Settings](#value-display-alert-settings)
      - [Advanced Value Display Usage - PBX Output](#advanced-value-display-usage---pbx-output)
    - [Bar Display](#bar-display)
      - [Bar Display Common Settings](#bar-display-common-settings)
      - [Bar Display Settings](#bar-display-settings)
      - [Bar Display Alert Settings](#bar-display-alert-settings)
    - [Round Scale](#round-scale)
      - [Round Scale Common Settings](#round-scale-common-settings)
      - [Round Scale Style Settings](#round-scale-style-settings)
      - [Round Scale Alert Settings](#round-scale-alert-settings)
    - [Bit Panel](#bit-panel)
      - [Bit Panel Common Settings](#bit-panel-common-settings)
      - [Bit Panel Style Settings](#bit-panel-style-settings)
      - [Bit Panel Alert Settings](#bit-panel-alert-settings)
      - [Advanced Bit Panel Usage - PBX Output State](#advanced-bit-panel-usage---pbx-output-state)

### Value Display

![Value Display Example](images/Instrument%20Panel%20-%20Value%20Display.png)[]

#### Value Display Common Settings

The *Value Display* can be configured with the following settings:
![Value Display Common Settings](images/Instrument%20Panel%20-%20Value%20Display%20Common%20Settings.png)

- Channel: Defines the channel data that the element will present
- Caption: Allows an alternate 'channel name' to be displayed
  - This is useful in the event the measured channel name is not descriptive / long
- Number Format: Defines the number of digits, number decimals, and scaling that will be used
- Gauge/Caption: Control the base colors of the display element
- Upper/Mid/Lower Range: Control the color of the display element based on the current cursor position value of the channel.

#### Value Display Alert Settings

The *Value Display* can be configured to visually alert the user based on the channel value.
![Value Display Alert Settings](images/Instrument%20Panel%20-%20Value%20Display%20Alert%20Settings.png)

- Hysteresis: the value the channel must change in order to clear a triggered alert
  - Example Engine Water Temperature: Hysteresis value = 2 and Upper range = 100
    - The Alert will trigger when the channel value goes above 100
    - The Alert will clear when the channel value goes below (100 - 2) = 98
- Upper/Mid/Lower Range: Toggle alerts based on the values on the *Common Settings* screen.
- Time Controls: Define time based automatic clearing of alerts or retriggers

#### Advanced Value Display Usage - PBX Output

Value Displays can be configured to show an enumeration of the channel. This can be very useful for error channels where a text value is more descriptive than an error code.

![Value Display Example](images/Instrument%20Panel%20-%20Value%20Display%20Example.gif)

Tutorial:

1. Enter the Tools &rarr; Channels Settings Window
2. Select the channels of interest (in our case *PBX Output State*) ![Channel Settings Window](images/Instrument%20Panel%20-%20Value%20Display%20Example%202.png)
3. Change the 'Format' cells to 'Other Formatters -> More'
4. Create a [channel formatter](./Channel%20Settings#channel-format) for *PBX Output States* ![Channel Formatter Setting](images/Instrument%20Panel%20-%20Value%20Display%20Example%201.png)
5. Add the channel as a *Value Display* to your instrument panel

Pitfall: The formatter is a global setting, so if you go to an Oscilloscope and change the *Channel Format* back to display a number, your instrument panel will also change back to a number

![Value Display Properties](images/Instrument%20Panel%20-%20Value%20Display%20Example%203.png)

### Bar Display

![Bar Display Example](images/Instrument%20Panel%20-%20Bar%20Display.png)

#### Bar Display Common Settings

The *Bar Display* can be configured with the following settings:
![Bar Display Common Settings](images/Instrument%20Panel%20-%20Bar%20Display%20Common%20Settings.png)

- Channel: Defines the channel data that the element will present
- Caption: Allows an alternate 'channel name' to be displayed
  - This is useful in the event the measured channel name is not descriptive / long
- Number Format: Defines the number of digits, number decimals, and scaling that will be used
- Gauge/Caption: Control the base colors of the display element
- Upper/Mid/Lower Range: Control the color of the display element based on the current cursor position value of the channel.

#### Bar Display Settings

![Bar Display Settings](images/Instrument%20Panel%20-%20Bar%20Display%20Bar%20Settings.png)

- Orientation: Select between Horizontal and Vertical layout
- Shape of Color: Drawing controls for the *Bar Display*
- Peaks: Controls for visual indication of min/max values

#### Bar Display Alert Settings

The *Bar Display* can be configured to visually alert the user based on the channel valu. 
![Bar Display Alert Settings](images/Instrument%20Panel%20-%20Bar%20Display%20Alert%20Settings.png)

- Hysteresis: the value the channel must change in order to clear a triggered alert
  - Example Engine Water Temperature: Hysteresis value = 2 and Upper range = 100
    - The Alert will trigger when the channel value goes above 100
    - The Alert will clear when the channel value goes below (100 - 2) = 98
- Upper/Mid/Lower Range: Toggle alerts based on the values on the *Common Settings* screen.
- Time Controls: Define time based automatic clearing of alerts or retriggers

### Round Scale

![Round Scale Example](images/Instrument%20Panel%20-%20Round%20Scale.png)

#### Round Scale Common Settings

The *Round Scale* can be configured with the following settings:
![Round Scale Common Settings](images/Instrument%20Panel%20-%20Round%20Scale%20Common%20Settings.png)

- Channel: Defines the channel data that the element will present
- Caption: Allows an alternate 'channel name' to be displayed
  - This is useful in the event the measured channel name is not descriptive / long
- Number Format: Defines the number of digits, number decimals, and scaling that will be used
- Gauge/Caption: Control the base colors of the display element
- Upper/Mid/Lower Range: Control the color of the display element based on the current cursor position value of the channel.

#### Round Scale Style Settings

![Round Scale Settings](images/Instrument%20Panel%20-%20Round%20Scale%20Style%20Settings.png)

- These are self explanatory

#### Round Scale Alert Settings

The *Round Scale* can be configured to visually alert the user based on the channel value.

![Round Scale Alert Settings](images/Instrument%20Panel%20-%20Round%20Scale%20Alert%20Settings.png)

- Hysteresis: the value the channel must change in order to clear a triggered alert
  - Example Engine Water Temperature: Hysteresis value = 2 and Upper range = 100
    - The Alert will trigger when the channel value goes above 100
    - The Alert will clear when the channel value goes below (100 - 2) = 98
- Upper/Mid/Lower Range: Toggle alerts based on the values on the *Common Settings* screen.
- Time Controls: Define time based automatic clearing of alerts or retriggers

### Bit Panel

![Bit Panel Example](images/Instrument%20Panel%20-%20Bit%20Panel.png)

#### Bit Panel Common Settings

The *Bit Panel* can be configured with the following settings:
![Bit Panel Common Settings](images/Instrument%20Panel%20-%20Bit%20Panel%20Common%20Settings.png)

- Channel: Defines the channel data that the element will present
- Caption: Allows an alternate 'channel name' to be displayed
  - This is useful in the event the measured channel name is not descriptive / long
- Bit Panel Layout: Control the shape/layout of the bit panel
- Colors: control the Bit Panel level color settings (can be override on the *Bit Settings* tab)

#### Bit Panel Style Settings

![Bit Panel Settings](images/Instrument%20Panel%20-%20Bit%20Panel%20Bit%20Settings.png)

- Overrides for individual bits
  - Provide the displayed name / color settings for each bit.

#### Bit Panel Alert Settings

The *Bit Panel* can be configured to visually alert the user based on the channel value.

![Bit Panel Alert Settings](images/Instrument%20Panel%20-%20Bit%20Panel%20Alert%20Settings.png)

- Alert: Define which bits provide alerts
- Time Controls: Define time based automatic clearing of alerts or retriggers.

#### Advanced Bit Panel Usage - PBX Output State

Using PBX Output State as an example, you can define the Bit Panel to present the Output State of a PBX output in a user friendly way:

|||
|---|---|
|![Bit Panel PBX Example](images/Instrument%20Panel%20-%20Bit%20Panel%20PBX%20Output.png)|![Bit Panel PBX Example](images/Instrument%20Panel%20-%20Bit%20Panel%20PBX%20Output%202.png)|

Tutorial:

Step 1:
 - Create a filter/default Math Function:

```
2 ^ ({Default} + 4)
```

- Name it "pbx"

Step 2:

- Add a *Bit Panel* to your *Instrument Panel*

Step 3:

- Define the name of your channel

![Bit Panel Example 1](images/Instrument%20Panel%20-%20Bit%20Panel%20Example%201.png)

- Add the text "-pbx" to the name (this applies the [Default channel](./Math%20Functions#default-channels))
![Bit Panel Example 2](images/Instrument%20Panel%20-%20Bit%20Panel%20Example%202.png)

Step 4:

- Configure the *panel layout* and *Bit Settings*

![Bit Panel Layout](images/Instrument%20Panel%20-%20Bit%20Panel%20Example%203.png)
![Bit Panel Layout](images/Instrument%20Panel%20-%20Bit%20Panel%20Example%204.png)