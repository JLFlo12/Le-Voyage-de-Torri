<div align="center">

# Le Voyage de Torri

**Torri's Journey: a third-person 3D game made with Unreal Engine 5.7**

🇬🇧 English · [🇫🇷 Français](README.fr.md)

![Unreal Engine](https://img.shields.io/badge/Unreal%20Engine-5.7-0E1128?logo=unrealengine&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?logo=cplusplus&logoColor=white)
![Blueprints](https://img.shields.io/badge/Blueprints-visual%20scripting-1E90FF)
![Platform](https://img.shields.io/badge/Platform-Windows-0078D6)
![License: MIT (code)](https://img.shields.io/badge/License-MIT%20(code)-yellow.svg)

</div>

---

## About

*Le Voyage de Torri* is a personal third-person 3D game built with **Unreal Engine 5.7**, using both **Blueprints** and **C++**. You explore a stylized natural world, a tropical rainforest and an obstacle course with moving platforms.

## Features

- **Main menu** to start a game, change options, view the credits or quit, with a loading screen and a pause menu
- **Settings** for general, graphics, audio and controls. The key bindings are listed in *Options > Controls*.
- **A stylized nature world** to explore, with butterfly, falling leaf and wind effects
- **A tropical rainforest** level
- **An obstacle course** with platforms that move and rotate, driven by C++ code

## Levels

| Level | Map | Description |
| --- | --- | --- |
| Main menu | `Content/Stylized_Nature_Set/MainMenu/MainMenu` | Start map of the game and the editor |
| Nature world | `Content/Stylized_Nature_Set/Demo/Maps/Demo_Level` | Main level, launched from the menu |
| Rainforest | `Content/Rain_Forest/Maps/Rain_Forest` | Tropical forest |
| Obstacle course | `Content/ObstacleAssault/Maps/Main` | Moving and rotating platforms |

## Requirements

- **Windows 10/11**
- [Unreal Engine 5.7](https://www.unrealengine.com/download), installed with the Epic Games Launcher
- **Visual Studio 2022** with the *Game development with C++* workload, needed to compile the project's C++ code. The project's `.vsconfig` file suggests the right components when you open it.
- About **10 GB** of free disk space: ~3 GB for the repository, the rest for compilation and shaders

## Installation

1. Clone the repository (~2.6 GB download):

   ```bash
   git clone --depth 1 https://github.com/JLFlo12/Le-Voyage-de-Torri.git
   ```

   `--depth 1` skips the Git history, which makes the download faster.

2. Open `Le Voyage de Torri-main/ObstacleAssault.uproject`.
3. When Unreal asks to rebuild the *missing modules*, click **Yes**.
4. The first launch compiles the shaders, which can take a while.
5. The project opens on the main menu. Click **Play** in the editor, then start a game from the menu.

> [!TIP]
> To test a single level, open its map from the Content Browser (see [Levels](#levels)) and click **Play**.

## Project structure

The Unreal project lives in the `Le Voyage de Torri-main/` folder.

| Folder | Contents |
| --- | --- |
| `Source/ObstacleAssault` | C++ code (moving platforms) |
| `Content/Stylized_Nature_Set/MainMenu` | Main menu map and widgets (game start) |
| `Content/Stylized_Nature_Set/Demo/Maps` | Main level, launched from the menu |
| `Content/Rain_Forest` | Rainforest level |
| `Content/ObstacleAssault` | Obstacle course and its Blueprints |
| `Content/…` | Other asset packs used by the levels (see [Credits](#credits)) |
| `Config` | Project configuration (start map, inputs…) |
| `Plugins/VisualStudioTools` | Microsoft plugin for Visual Studio integration |

## C++ code

The `AMovingPlatform` class ([MovingPlatform.h](Le%20Voyage%20de%20Torri-main/Source/ObstacleAssault/MovingPlatform.h), [MovingPlatform.cpp](Le%20Voyage%20de%20Torri-main/Source/ObstacleAssault/MovingPlatform.cpp)) moves and rotates a platform every frame. When the platform has travelled further than `MaxMoveDistance`, it turns back.

You can set three properties directly in the editor:

| Property | Type | Role |
| --- | --- | --- |
| `MoveVelocity` | `FVector` | Direction and speed of movement |
| `MaxMoveDistance` | `float` | Distance travelled before the platform turns back |
| `RotationVelocity` | `FRotator` | Rotation speed |

## Credits

**Assets:** Stylized Nature Set, Rain Forest, Minimalistic Menu and Vefects Easy Impact Frames (Fab / Unreal Marketplace), plus Learning Kit Games, Learning Kit Robots and Hour of Code (Epic Games).

These assets belong to their authors and are subject to their own licenses.

## License

The original code in this repository (mainly `Source/`) is released under the [MIT License](LICENSE).
Third-party assets and plugins are **not** covered by this license (see [Credits](#credits)).
