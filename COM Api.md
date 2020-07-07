# WinDarab COMApi

- [WinDarab COMApi](#windarab-comapi)
  - [API Documentation](#api-documentation)
  - [Sample Files](#sample-files)
  - [Registering the API with Windows](#registering-the-api-with-windows)
    - [DarabRegClean](#darabregclean)
    - [DarabRegister](#darabregister)
    - [DarabUnRegister](#darabunregister)
  - [Creating COMAPI vs BMS2API](#creating-comapi-vs-bms2api)
  - [Opening Telemetry Data](#opening-telemetry-data)

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
WinDarabApp = actxGetRunningServer('BMS2Api.Application');
```

``` C#
// BMS2API in C#
var comType = Type.GetTypeFromProgID("BMS2Api.Application");
dynamic application = Activator.CreateInstance(comType);
```

## Opening Telemetry Data

The best practice to open telemetry data is to pass the telemetry URI to the Application.OpenDataFile:

```C#
# C# example
string serverName = "Users Computer"; # the name of the PC hosting WDServer
string carName = "My Car"; # the name of the 'Car' in WDServer
string path = $"\\.\Telemetry\{serverName}\{carName}";

var app = new WinDarab.Application();
var telemetryFile = app.OpenDataFile(path);
```

More to come
