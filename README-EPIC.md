# Unreal Public Source Distribution

## Copyright

All files contained here are the property of [Epic Games, Inc](http://www.epicgames.com).
They are provided without warranty, and under the same terms as the Unreal retail license
agreement: You may use them for your personal, non-profit enjoyment, but you may not sell
or otherwise commercially exploit the source or things you created based on the source.

## Installation

Unzip the source distribution into your root Unreal directory, for example `c:\Unreal`. You
*must* use the exact same version of Unreal patch and public source distribution. If you
have different versions, the the DLL's you recompile with the source distribution will
almost certainly fail to run.

## Tools Required

To recompile the source, you must have Microsoft Visual C++ 6.0, either with no service
packs, or with SP1. The source does not work with previous versions of Visual C++. The
source may or may not work with subsequent versions and service packs. If you are using
anything other than this exact version, don't even think about emailing us asking why it
doesn't work.

## How Each Package (.DLL) Is Structured

Unreal packages are described in detail in the [Package Documentation][1]. The source code
for each package (for example, `MyPackage`) that contains a C++ .DLL component is as follows:

* `C:\Unreal\MyPackage\Src\MyPackage.dsp`: Microsoft Developer Studio project files.
* `C:\Unreal\MyPackage\Src\*.cpp`: C++ source code.
* `C:\Unreal\MyPackage\Src\*.h`: Private C++ header files, which are only used internally by
  this package.
* `C:\Unreal\MyPackage\Classes\*.upkg`: UnrealScript package definition file.
* `C:\Unreal\MyPackage\Classes\*.uc`: UnrealScript class source files.

## Directory Structure

* `\Unreal\UnrealPubSrc.dsw`: Microsoft Visual C++ workspace file.
* `\Unreal\Core`: Unreal engine core components (non-game code, such as low-level object
  handling, script interpretter, file processing, configuration, and platform-specific
  support).
* `\Unreal\Engine`: Unreal engine game components.
* `\Unreal\Setup`: Unreal Windows installer/uninstaller (`Setup.exe`).
* `\Unreal\GlideDrv`: Unreal Glide support. Note: To compile this code, you need the latest
  version of the Glide SDK from 3dfx's web site.
* `\Unreal\Help`: A small amount of documentation.
* `\Unreal\Launch`: Unreal Windows startup code (`Unreal.exe`).
* `\Unreal\OpenGLDrv`: Unreal's OpenGL support.
* `\Unreal\System`: Unreal's system directory.
* `\Unreal\UCC`: Platform-neutral command line runner. Launches *commandlets* such as the
  script compiler, installation generator, and command-line server.
* `\Unreal\Window`: Windows encapsulation.

## Additional Documentation

Visit the [Unreal Technology Page][2] for our complete online documentation.

## End

[1]: Help/PACKAGES.md
[2]: https://web.archive.org/web/20040728054606/http://unreal.epicgames.com/
