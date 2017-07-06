This is a small guide for extracting or modifying assets or code from games made in unity engine

1. [Unity game folder structure](#unity-game-folder-structure)
2. [Extracting and editing code](#extracting-and-editing-code)
3. [Extracting assets](#extracting-assets)

## Unity game folder structure

The folder structure of a game built with Unity 5 (Windows target) :

```
│   *.exe
└───*_Data
    │   globalgamemanagers
    │   globalgamemanagers.assets
    │   level0
    │   level0.resS
        ...
    |   levelN
    |   levelN.resS
    │   sharedassets0.assets
    │   sharedassets0.assets.resS
        ...
    |   sharedassetsN.assets
    |   sharedassetsN.assets.resS
    |   resources.assets
    ├───Managed
    │       Assembly-CSharp.dll
    │       Assembly-UnityScript.dll
    │       Mono.Security.dll
    │       mscorlib.dll
    │       System.Core.dll
    │       System.dll
    │       UnityEngine.dll
    │       UnityEngine.dll.mdb
    │       UnityEngine.Networking.dll
    │       UnityEngine.UI.dll
    ├───Mono
    │   │   mono.dll
    │   └───etc
    │       └───mono
    │           │   browscap.ini
    │           │   config
    │           ├───1.0
    │           │       DefaultWsdlHelpGenerator.aspx
    │           │       machine.config
    │           ├───2.0
    │           │   │   DefaultWsdlHelpGenerator.aspx
    │           │   │   machine.config
    │           │   │   settings.map
    │           │   │   web.config
    │           │   └───Browsers
    │           │           Compat.browser
    │           └───mconfig
    │                   config.xml
    └───Resources
            unity default resources
            unity_builtin_extra
```

\* : Name chosen during building

File/Directory | Description
--- | ---
*.exe | Executable file of the game
*_Data | Data folder containing the game resources
level0-levelN | Files containing game scenes data, each scene has its own file
sharedassets0-sharedassetsN | Game assets are split into sharedassets and .resS files
resources.assets | Assets found in the project resources folders and their dependencies are stored in this file
Managed | Folder containing unity DLLs
Assembly-CSharp.dll | DLL file containing compiled C# files
Assembly-UnityScript.dll | DLL file containing compiled UnityScript files

## Extracting and editing code

C# and UnityScript files are compiled into the Assembly-CSharp.dll and Assembly-UnityScript.dll DLLs respectively, which can be found inside the Managed folder.

DDLs can be decompiled using [ILSpy](http://ilspy.net/) or [dnSpy](https://github.com/0xd4d/dnSpy) which allow modifying and recompiling assembly files.

<a href="https://github.com/xcsh/Unity-game-hacking/wiki/images/dnspy.png"><img src="https://github.com/xcsh/Unity-game-hacking/wiki/images/dnspy.png" width="450"></a>

## Extracting assets

Assets are stored in the .assets .resS files. Content of these files can be unpacked with one of these tools :

Tool | Description
--- | ---
[Unity Assets Explorer](http://zenhax.com/viewtopic.php?f=9&t=36) | Can extract textures to .DDS format, meshes to .43 format.
[DisUnity](https://github.com/ata4/disunity) | Command-line tool in java that can extract raw data.
[Unity Assets Bundle Extractor](https://7daystodie.com/forums/showthread.php?22675-Unity-Assets-Bundle-Extractor) | UABE is a tool that allow modification of assets file and extraction of assets in usable formats (png/tga for textures, obj for meshes).
[Unity Studio](https://github.com/RaduMC/UnityStudio) | A tool for exploring, extracting and exporting assets from Unity games and apps.
[QuickBMS](http://aluigi.altervista.org/quickbms.htm) with [this script](http://aluigi.altervista.org/bms/unity.bms) |

#### DDS files :

The [DDS](https://en.wikipedia.org/wiki/DirectDraw_Surface) files can be opened/converted/edited with this [gimp plugin](http://registry.gimp.org/node/70) or this [photoshop plugin](https://developer.nvidia.com/nvidia-texture-tools-adobe-photoshop).

#### Another way of extracting meshes and textures :

Use [3D Ripper DX](http://www.deep-shadows.com/hax/3DRipperDX.htm) (doesn't support 64 bits binaries) or [Ninja Ripper](http://cgig.ru/en/2012/10/ho-to-use-ninja-ripper/).
