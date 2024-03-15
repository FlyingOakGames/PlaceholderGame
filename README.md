# PlaceholderGame

A placeholder game that you don't need to build yourself (Github Actions will do it for you) for Windows, Linux, and macOS to upload to your Steam depots for whatever reason.

Made with [MonoGame](https://monogame.net/) and leveraging .NET 8 ```PublishAot``` feature.

This project also acts as a cross-platform MonoGame template.

# How to use

- Fork the project
- Edit [empty.png](PlaceholderGame/Content/empty.png) to your liking
- Push the changes to Github
- Wait for the Actions to complete and download the generated artifacts from there
- Upload those builds to Steam

# MonoGame template

This project can be used as a MonoGame template to build cross-platform applications and package them automatically with Github Actions.

Whenever you push commits, Actions will build the game for all operating systems (natively using NativeAOT).

## How does it work?

- The [.csproj](PlaceholderGame/PlaceholderGame.csproj) is configured so that NativeAOT only runs when publishing projects and only on systems it can run (avoid cross-compilation errors)
- A [post-build script](PlaceholderGame/post_build.ps1) is creating the macOS App Bundle
- Github [Actions](.github/workflows/build.yml) is used to build the game and fuse macOS x64 and arm64 binaries into one universal binary supporting both
