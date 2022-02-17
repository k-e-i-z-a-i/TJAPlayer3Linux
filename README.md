# TJAPlayer3Linux
Running TJAPlayer3 on Linux.

## Non-Native Play

[The preconfigured version of TJAPlayer by Meowgister](https://tjadataba.se/tjap/) can be successfully run using [Lutris](https://lutris.net/) through the following steps:

1. Download and install the Dom Casual Std + DFPKanteiryu-XB (DFB勘亭流-XB) font, [which is available here](https://tjadataba.se/). It might also be required to have Japanese enabled as language on your Linux machine.

2. Create a folder named "TJAPlayer3" in the "\~Home/Games" directory used by Lutris.

3. Create a folder named "game" in the "\~Home/Games/TJAPlayer3" directory you just created.

4. Place all of the TJAPlayer3 game folders and files into the "\~Home/Games/TJAPlayer3/game" directory you just created.

5. Open Lutris and click on "Add Game" (the plus symbol in the top left corner).

8. Under "Game Info", set the runner to "Wine" and name the game.

9. Under "Game Options", set:

      a) Executable to "\~Home/Games/TJAPlayer3/game/TJAPlayer3.exe",

      b) Wine prefix to "\~Home/Games/TJAPlayer3", and

      c) Prefix architecture to "32-bit".

10. Under "System Options" add a new "Environment variable" with a Key of "LANG" and Value of "ja\_JP.UTF-8".

11. Save your changes.

12. Run/play the game in order to initialize a wineprefix for the game. It will not successfully run because dependencies are missing but this is a required step.

13. In Lutris, select your newly created TJAPlayer3 profile, then next to the wine glass icon, click on the dropdown menu button and choose "Open Bash terminal". Enter the following command:

```
winetricks --force dotnet48 cjkfonts gdiplus
```

After following these steps, the simulator should work on your machine.

[OpenTaiko](https://github.com/0auBSQ/OpenTaiko/blob/main/README-EN.md) almost ran after using the above steps and installing the "MS UI Gothic" font, but a SlimDX error prevents it from successfully running.

Credit to [Katoumegumi](https://wiki.archlinux.org/title/User:Katoumegumi) and chloe" on Discord for their assistance.

**Also,** Katoumegumi recommends the following in order to resolve audio latency problems:

* [Do not enable "Reduce PulseAudio latency"](https://wiki.archlinux.org/title/User:Katoumegumi#Additional_tweaks), and
* [Switching to Pipewire.](https://wiki.archlinux.org/title/User:Katoumegumi#(Optional)_Switching_to_PipeWire)

## Native Play

* [TJAPlayer3-f](https://github.com/Mr-Ojii/TJAPlayer3-f/releases) runs natively on Linux but its code needs to manually changed in order to be able to do anything other than autoplay. [This is the required code](https://github.com/FAKEYJSNPI/TJAPlayer3-f/commit/49bb7ae2a7ad5461186a25f26240a822a602326a) but it needs to be implemented and compiled, which is a real barrier to entry for many. This fork will likely never be made playable by default.

* There are apparently plans to make [TJAPLayer3GL](https://github.com/FAKEYJSNPI/TJAPlayer3-f/commit/49bb7ae2a7ad5461186a25f26240a822a602326a) playable on Linux, but no roadmap or timeline has been made available.

* [OpenTaiko](https://github.com/0auBSQ/OpenTaiko/blob/main/README-EN.md)'s maintainer has also expressed interest on Discord in eventually bringing native support for this simulator to Linux.

## Other Simulators

The only other good option available to Linux users is to run your own [Taiko Web](https://github.com/bui/taiko-web) server and access it through Chrome (locally or otherwise) on your Linux machine.

For the best Taiko Web experience you need to enable GPU rasterization in Chrome flags because it is off by default. Credit to Katie Frogs on Discord for this suggestion.
