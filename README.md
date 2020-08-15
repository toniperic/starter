# Starter
I want my Macbooks to look and behave pretty much identically.
This repo helps me provision them as fast as possible with as minimum manual effort as possible.

_Ran and tested on macOS Catalina (10.15)._

## How does it work?
It's basically just a Bash script that installs and configures a bunch of software, such as Command line tools, Homebrew, Git, Fish Shell, as well as configuring a bunch of system settings to my likings.

## Usage
Just run `bash bootstrap`

You can provide environment variables in order to make additional configuration, such as altering your global Git configuration, changing which Fish shell version you'd prefer to install etc.

All configuration options are documented below.

### Fish Shell
To install a specific version, set the `FISH_TARGET_VERSION` variable:  
`FISH_TARGET_VERSION=3.0.0 bash bootstrap`

Defaults to `3.1.2`.

### Git
Set the `GIT_NAME` variable to change global Git name (user.name config key):  
`GIT_NAME="John Doe" bash bootstrap`

Set the `GIT_EMAIL` variable to change global Git email (user.email config key):  
`GIT_EMAIL=john@example.com bash bootstrap`

### Timezone
Set the `TARGET_TIMEZONE` variable to change system's timezone settings.
Use `sudo systemsetup -listtimezones` to find valid values.

Defaults to `Europe/Zagreb`.

## To-do
I haven't managed to automate absolutely every single step yet (or don't want to automate some of the things), so for the time being I keep a list of things I need to take care of:
- require password immediately after sleep system config
- GPG keys + Git signing
