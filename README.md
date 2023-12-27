# Pong, written in Monogame

This is mainly a learning experience for me, to improve my understanding of the Monogame framework.
I am following a [tutorial by HadiCya](https://hadicya.dev/building-pong-with-monogame-a-step-by-step-guide).
They have posted [their code](https://github.com/HadiCya/Pong-MonoGame) on github as well.


# Hacks for M1 Mac

When I went to add the font to display the score, I ran into a couple of issues.

First, starting the content editor via `dotnet mgcb-editor` would do nothing.
To get this working, I installed the x64 version of the SDK, as recommended [here](https://community.monogame.net/t/mgcb-not-launching-on-macos-m1/17948/2).

Second, once the font was added, the build would fail with the following exception:
```
System.DllNotFoundException: Unable to load shared library 'freetype6' or one of its dependencies.
```
To resolve this, I followed the suggestion by `sezdev` in [this thread](https://community.monogame.net/t/textureimporter-error-mac-os-monterey-12-6/18049/25).
In Rider, go to `Settings > Build, Execution, Deployment > Toolset and Build`, and change the SDK

In Rider, go to `Rider -> Preferences -> Build, Execution, Deployment -> Toolset and Build` and change the `.NET CLI executable path`
to `/usr/local/share/dotnet/x64/dotnet` (it is a drop-down). This is saved in the `Pong.sln.DotSettings.user` file.
The game will now run from within Rider.
It does NOT run from the command-line.

