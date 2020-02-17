# Special Channels

- [Special Channels](#special-channels)
  - [Internal Channels](#internal-channels)
  - [Special channels settings](#special-channels-settings)
  - [Defining a special channels list](#defining-a-special-channels-list)

## Internal Channels

  In addition to defining recorded channels WinDarab also defines its own, internal channels. Apart from some exceptions, internal channels are treated like recorded channels.
The following table lists all internal channels and their descriptions:
|Channel|Description|
|:---:|:---|
|laptrig|when vehicle is passing lap trigger, otherwise 0|
|Mux|Row values identifier  (Reader/CanCard)|
|Block number|(CardMemory)|
|samples|Record Number/ Samples <br>Channel has a special plotting routine, plotting every record as a single dot.|
|xdist|Distance axis<br>Logged distance travelled will be standardised to accord with the course length-- if the difference between the actually logged lap length and specified lap length is less than 5 %.<br>If the channel has not been recorded directly, it will be calculated using values from rawdist and laptrig.|
|xtime|Time axis|
|lapdist|Distance travelled on the course since last lap trigger.|
|laptime|Time logged since last lap trigger.|
|rawdist|Logged distance|

### Card Memory Only <!-- omit in toc -->

|Channel|Description|
|:---:|:---|
|dbg_time|Block time stamp<br>(CardMemory with active debug switch only)|
|dbg_dist|Block distance stamp<br>(CardMemory with active debug switch only)|

### Note <!-- omit in toc -->

- Some channels may not be available depending on the hardware you use and its configuration.

## Special channels settings

WinDarab provides the user the possibility to define a list of special channels for the following categories:
|Category|Description|
|:----:|:---|
|Distance|Contains channels or calculation methods WinDarab should use to generate distance information. Predefined calculation methods are “Calculate using GPS”, “Calculate using speed” and “Default distance”.|
|Speed|List of channels, which contain speed information. If a file contains one of the channels in the list, it will be used in other calculation (e.g. calculation of the distance information).<br>Predefined channels are “vfz_w”, “vfzg” and “speed”.|
|GPS Horizontal (meter)|List of channels, which contain horizontal GPS-coordinates containing data, which is transformed into relative meters.|
|GPS Vertical (meter)|List of channels, which contain vertical GPS-coordinates containing data, which is transformed into relative meters.|
|GPS Height(meter)|List of channels containing GPS-height in meters.|
|GPS Longitude (Earth)|List of channels, which contain the longitude of the |GPS-coordinates. The channel “gps_long” is predefined.
|GPS Latitude (Earth)|List of channels, which contain the latitude of the |GPS-coordinates. The channel “gps_lat” is predefined.
|GPS Height(Earth)|List of channels, which contain the height of the GPS-coordinates. The channel “gps_alt” is predefined.|

The user can selects special channels for each category. WinDarab uses these lists to find channels containing needed information. If a file contains one of the channels listed it will be used for further calculations. If a file contains more than one of the channels in the list, the user selects must select one.

## Defining a special channels list

To define special channels for the categories listed above or to modify a special channels list, follow these steps:

<p align="center">
<img src="images/Define Special Channels.jpg">
</p>

1. Use “Tools &rarr; Settings &rarr; Program” to open the “Options” dialog box.
2. Select the “Special channels” tab.
3. Select the category from the “Special channels for” – list.
4. The “Special channels” tab contains two channel lists - list of all channels in the measurement file and list of special cannels for the selected category.

- To add a channel to special channels list:
  - Select the channel from the list of all channels and click on the ![Add Button](images/Special%20Channels%20Add%20Button.jpg) button.
- To delete a channel from the special channel list:
  - Select the channel from the special channel list and click on the
  ![Delete Button](images/Special&#32;Channels&#32;Delete&#32;Button.jpg) -button.

The channels and the calculation methods in the special channel list have a priority. The position of a channel in the list determines its priority. The higher the position of a channel in the list, the higher the priority. The user can change the priority of a channel or calculation method as follow:

1. Select the desired channel in the list
2. Place the channel to the desired position by using the **up** and **down** arrow buttons

### Note: <!-- omit in toc -->

- The reserved entries in a special channel list cannot be removed.
- For distance generation information is valid - the calculation methods always have a higher priority than the channels selected by the user.
- If the channel provided for distance information was not sampled with each sample block, the interpolation of the channel for each sample position was not “good” enough, if the channels quantization didn’t offer enough precision for the interpolated values.
- The channels provided for distance generation shall be monotonically strictly increased (derivative > 0). Except the first two samples of the channel. In this very special case the first sample will be extrapolated based on the values of the second and third sample. WinDarab carries out additional checks to ensure this and shows a message, if a distance channel cannot be used.
- If the distance channel isn’t strictly increasing, WinDarab interpolates the duplicate values and saves the results to the file. This is done once when the channel is accepted as distance channel.
- If distance information is calculated by GPS (the calculation method “Calculate using GPS” is selected) and WinDarab runs with a unit converter for the distance channel, the lap normalization is not working in the case the user changes the current racetrack. Only in this case the data is not normalized (but as measured!).