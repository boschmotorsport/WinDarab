# WinDarab COMApi

- [WinDarab COMApi](#windarab-comapi)
  - [API Documentation](#api-documentation)
  - [Sample Files](#sample-files)
  - [Registering the API with Windows](#registering-the-api-with-windows)
    - [DarabRegClean](#darabregclean)
    - [DarabRegister](#darabregister)
    - [DarabUnRegister](#darabunregister)
  - [COMAPI vs BMS2API](#comapi-vs-bms2api)
    - [COMAPI](#comapi)
    - [BMS2API](#bms2api)
  - [Creating COMAPI vs BMS2API](#creating-comapi-vs-bms2api)
    - [API in C / C++ / C&#35;](#api-in-c--c--c)
      - [C / C++](#c--c)
      - [C&#35;](#c)
  - [Opening Telemetry Data](#opening-telemetry-data)
  - [Updating Virtual Channels](#updating-virtual-channels)
  - [COMAPI Can Create New Measurement Files](#comapi-can-create-new-measurement-files)

## API Documentation

Full documentation for the API calls can be found from WinDarab
![Full Help](images/COMAPI&#32;Show&#32;Help.jpg)

## Sample Files

Sample files are available in:

- C#
- VBA/Excel
- Matlab

These can be found on your computer at:_\<WinDarab Install>/Samples_

## Registering the API with Windows

WinDarab automatically registers the COMAPI and BMS2API with Windows on installation.
However, some users run multiple installs of WinDarab and COMAPI/BMS2API can only be registered to a single install of WinDarab. If this is the case, we provide three batch scripts:

1. DarabRegClean.cmd
2. DarabRegister.cmd
3. DarabUnregister.cmd

These must be run with *Administrator* privileges.

### DarabRegClean

This is scripts solves a problem from much older WinDarab versions < 7.4, it unregisters any (and all) versions of WinDarab from the Windows registry. Then it registers the version of WinDarab from the executing directory of the script.

### DarabRegister

This script triggers WinDarab to register the version contained in the executing directory

### DarabUnRegister

This script removes the registration of the Darab contained in the executing directory

## COMAPI vs BMS2API

### COMAPI

Using COMAPI allows some control over WinDarab:

- Attaching to or creating new instances of WinDarab Applicatnoi
- Data Domain (opened files and overlays)
- Cursor position
- View range
- Marked/Tagged range

A user can also compile their application as a *WinDarab Plugin* this allows custom buttons and menus on the WinDarab Ribbon

With the exception of plugins, applications using COMAPI are *out of process communication*

### BMS2API

Using BMS2API allows the user to have *in process communication*.

When using BMS2API, there is no WinDarab Application that is spawned or interacted with. This is prefered if the user needs to access purely the data stored in a WinDarab datafile for external processing

## Creating COMAPI vs BMS2API

``` Matlab
% COMAPI in Matlab
WinDarabApp = actxGetRunningServer('WinDarab.Application');
```

``` C#
// COMAPI in C#
var comType = Type.GetTypeFromProgID("WinDarab.Application");
dynamic application = Activator.CreateInstance(comType);
```

``` Matlab
% BMS2API in Matlab
WinDarabApp = actxserver('BMS2Api.Application');
```

``` C#
// BMS2API in C#
var comType = Type.GetTypeFromProgID("BMS2Api.Application");
dynamic application = Activator.CreateInstance(comType);
```

### API in C / C++ / C&#35;

#### C / C++

Header files are now included to aid in application/plugin development

#### C&#35;

Adding a reference via COM to either the BMS2API or WinDarab (COMAPI) is preferred. This provides static type checking and syntax completion in Visual Studio / Visual Studio Code

## Opening Telemetry Data

The best practice to open telemetry data is to pass the telemetry URI to the Application.OpenDataFile:

```C#
// C# example
string serverName = "Users Computer"; // the name of the PC hosting WDServer
string carName = "My Car"; // the name of the 'Car' in WDServer
string path = $"\\.\Telemetry\{serverName}\{carName}";

var app = new WinDarab.Application();
var telemetryFile = app.OpenDataFile(path);
```

## Updating Virtual Channels

Important points:

- You cannot update the values of a virtual channel
  - You have to remove the virtual channel and then re-add it.
- The following sample shows a functional pattern.

```C#
void Main()
{
  // Get a reference to the currently running WinDarab
  // This is dangerous if you run multiple instances of WinDarab!
  var app = Application.GetActiveObject();

  //get the currently selected Datafile
  var dataFile = app.CurrentDomain.CurrentOverlay.DataFile;

  NewVirtualChannel(dataFile);
}


void NewVirtualChannel(WinDarabNet.DataFile df){
  var channelName = "my demo channel";

  // We need to remove the channel if we already made it
  RemoveChannelIfAlreadyMade(channelName,df);
  
  // Nominate a 'base' channel, we only need the Timeline from this channel
  var baseChannel = df.Channels["speed"];
 
  var channel = df.NewVirtualChannel();
  channel.Description = "Hi I'm a demo";
  channel.Source = "demo";
  channel.Name = channelName;
  channel.TimeLine = baseChannel.TimeLine;
  channel.IsPersistent = true;

  //create dummy data and fill the array
  double[] values = new double[baseChannel.TimeLine.TimeStampCount].Select(x => 4.0).ToArray();

  channel.SetPhysicalValues(0,values);
  channel.Publish();
}

void RemoveChannelIfAlreadyMade(string name, WinDarabNet.DataFile df)
{
  var channel = df.Channels[name];
  if (channel != null)
  {
    channel.DataFile.RemoveChannel(channel as WinDarabNet.Channel);
  }
}
```

## COMAPI Can Create New Measurement Files

- A 3rd party application/plugin can use the **UserDataFile** class to create new measurement files with application generated channel data.
- Files created with the new API are written in WinDarab file format v2 which is supported since WinDarab v7.6.
- A brief example how to write a file can be found in the BMS2ApiSamples.Net project, see the source in CreateUserDataFile.cs