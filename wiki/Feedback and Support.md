# Feedback and Support

Bosch Motorsport appreciates contructive feedback from WinDarab users. This feedback includes bug reports, feature requests, documentation requests, and more.

- [Feedback and Support](#feedback-and-support)
  - [Report Content](#report-content)
  - [Feedback Files](#feedback-files)
    - [Via WinDarab](#via-windarab)
    - [Via Windows Task Manager](#via-windows-task-manager)
    - [Via ProcDump Utility](#via-procdump-utility)
  - [Submitting The Bug Report](#submitting-the-bug-report)
  - [Bosch Motorsport Commitment to Continuous Improvement](#bosch-motorsport-commitment-to-continuous-improvement)

Bug reports can be created through WinDarab natively or in Windows Task Manager they can then be submitted to Bosch Motorsport for review. Bosch Motorsport is constantly working to improve WinDarab. If possible please use the [latest version](../releases) of WinDarab to see if your bug had already been resolved.

## Report Content

There are three components to maximize Bug Report effectiveness.

1. Problem Description
    - Video and Pictures Help
    - Work-flow to Reproduce Issue
    - Computer OS and WinDarab Version
2. Feedback Files
    - WinDarab Generated
    - Windows Generated
3. Supporting Files
    - Formulas
    - Desktop
    - Data Files

## Feedback Files

### Via WinDarab

Feedback files can be created by WinDarab in two ways. Both methods write the files to: **%WinDarab Install%/Minidump** folder location. If large data sets or desktops are open please give it some time, two zip files will be created for each feedback.
|||
|---|---|
|Automatic|WinDarab attempts to create crashdumps automatically when a crash is detected. If this happens the picture below will be shown when the crash occurs<br><p align="center"><img src="images/Feedback Crashdump Notice.jpg"></p>|
|Manual|**Press Left Ctrl + Right Shift + F10** and hold for 2 seconds. The window below will show up, click yes to create the crashdump.<br><p align="center"><img src="images/Feedback Crashdump Manual.jpg">
</p>|

### Via Windows Task Manager

Feedback files can also be created by Windows by pressing **Ctrl + Shift + Esc** then right click on the WinDarab process and select **Create Dump File**. This will create a .dmp file in a location specified by Windows. This method is usually only requried if WinDarab is unable to make its own file or Bosch Motorsport requests the Windows crashdump.
    ![Crashdump Windows](images/Feedback&#32;Windows&#32;Dump.jpg)

### Via ProcDump Utility

Rarely a crash occurs which the WinDarab built in feedback agent cannot catch and it is not possible to get to Windows Task Manager to get a .DMP file. If this occurs in a repeatable fashion:

1. Take note of what causes the crash and provide **detailed** notes on how to reproduce
2. Use the procdump.exe tool available from [Microsoft](https://docs.microsoft.com/en-us/sysinternals/downloads/procdump)
3. From the command line in Windows execute the following command (in the folder where the executable for procdump exists)

```bash
# The following command triggers procdump to start and watch the process 'darab.exe'
# If a crash occurs it will create a .dmp file
# ZIP the .dmp file and get it to your Bosch Motorsport contact
procdump -e -ma -w darab.exe
```

## Submitting The Bug Report

Send the [three parts](#report-content) of the crashdump to your Bosch Motorsport support representative via the method of your choosing. Recommended methods:

- Google Drive
- Dropbox
- Bosch Ad-Hoc Data Exchange Request

## Bosch Motorsport Commitment to Continuous Improvement

Feedback and support are always welcome, we are actively working to improve our software. To give feedback please contact your Bosch Motorsport dealer or support person.
