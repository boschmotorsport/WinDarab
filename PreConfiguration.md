# WinDarab Pre-Configuration

## Math Functions

A folder of **.BMSMTH* files can be added to the [default location](Math%20Functions#as-default-folder-button) for math functions.
The math functions can be organized and nested into sub-folders.

Users can specify an alternative [default location](Math%20Functions#as-default-folder-button) for math functions which can be a shared repository, a network drive (functions will be unavailable if the drive is disconnected), etc.

## Alias Channels

An alias channel settings file can be located in the [default location](Math%20Functions#as-default-folder-button) for Math Functions. This file is in standard XML format, so it can easily be checked into revision control software (git, svn, etc)

## Channel Settings

A channel settings file *Config/ChannelSettings.xml* can provided to users. Anything in the [Channel Settings](Channel%20Settings) dialog can be defined. This file is in standard XML format, so it can easily be checked into revision control software (git, svn, etc)

## Channel Colors

Similarly to [Channel Settings](#channel-settings) above, a channel colors file *Config/ChannelColors.xml* can be provided to users. This will allow consistent colors of channels for all users. This file is in standard XML format, so it can easily be checked into revision control software (git, svn, etc)

## Advanced Usecase

Users could use git to maintain common settings across multiple users. Changes to the above mentioned files/configurations could be easily tracked/shared.

Setup your base project:

1. Clone Repository from [WinDarab Base Configuration](https://github.com/boschmotorsport/WinDarab_Base_Configuration) into your WinDarab Install Directory
   - This is a base repository with only a *.gitignore* file.
2. Make your project specific settings
3. Commit your changes
4. Change the git remote to your repository
   - For more information on this topic, please contact Bosch Motorsport
5. Push changes

Provide your project to users in your organization:

1. Install WinDarab
2. Git Clone your repository into the install directory

### Multi-Project Advanced Usecase

The above could be expanded when looking at data from multiple projects for example:

- If a user is looking at data for a GT3 car and a drag car

Recommended Steps:

1. SCreate *Branch A* and copy files related to your project.
2. Commit this branch
3. Create a new branch *Branch B* with files related to project B
4. Commit this branch

Now you can easily switch between branches (This should be done with WinDarab shutdown)

### Pitfalls

- Don't forget to commit any changes as you work!
- Pulling updates will overwrite any un-committed changes