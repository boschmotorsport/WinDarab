# WinDarab COMApi

## API Documentation

Full documentation for the API calls can be found from WinDarab
![Full Help](images/COMAPI&#32;Show&#32;Help.jpg)

## Sample Files

Sample files are available in:

- C#
- VBA/Excel
- Matlab

These can be found on your computer at:_\<WinDarab Install>/Samples_

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
