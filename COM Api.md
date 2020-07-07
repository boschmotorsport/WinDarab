# WinDarab COMApi

- [WinDarab COMApi](#windarab-comapi)
  - [API Documentation](#api-documentation)
  - [Sample Files](#sample-files)
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
