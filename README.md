# theme-switcher

 A simple script that switches between dark and light theme at specified times.

## Why?

Because Pop!_OS has a dark and light theme, but no way to automate switching between those, I wrote a simple script that does that for me.

## Usage

Open the themeswitcher.sh in a text editor and configure the following:

- `LIGHT_THEME='Light-Theme-Name'` (name of the light theme)
- `DARK_THEME='Dark-Theme-Name'` (name of thedark theme)
- `HOUR_LIGHT=XX` (from when does the light theme apply)
- `HOUR_DARK=XX` (from when does the dark theme apply)

Then open `~/.profile` file and add following:

``theme-switcher

atqoutput=`atq`
if [ -z "$atqoutput" ]; then
  at XX:XX -f /path/to/theme/switcher/themeswitcher.sh 2> /dev/null
fi``

Where `XX:XX` is the time script is executed.

## Requirements

- **at** from package manager
- GNOME Desktop Environment

## To-Do

- [ ] Automatic .bashrc configurator
- [ ] Setup configurator

## License

This piece of code is published under MIT license. Feel free to do whatever you want with it.
