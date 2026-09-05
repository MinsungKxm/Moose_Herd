# Moose Herd

Moose Herd is a fixed-camera survival game built with Unity. Move sideways along the bottom of the screen and throw steaks at the animals approaching from above. Each steak removes an animal, but if even one animal gets past you, the game is over.

## Play or Download

- [Play Moose Herd in your browser on Unity Play](https://play.unity.com/en/games/5e9360d7-14a4-4a51-aebc-a1d22e8d4c9a/mooseherdweb)

Replace the placeholder URLs above after the game has been published.

## Table of Contents

1. [About the Game](#about-the-game)
2. [Gameplay](#gameplay)
3. [Features](#features)
4. [Controls](#controls)
5. [How to Play](#how-to-play)
6. [Installation](#installation)
7. [Playing the Web Version](#playing-the-web-version)
8. [Development](#development)
9. [Building the Project](#building-the-project)
10. [Project Structure](#project-structure)
11. [Known Limitations](#known-limitations)
12. [Credits](#credits)
13. [License](#license)

## About the Game

Moose Herd is a compact arcade-style survival game developed entirely with Unity. Random animals spawn near the top of the screen and move downward toward and past the player. The player's goal is to stop every animal before it reaches the bottom of the play area.

Unlike a third-person exploration game with a following camera, Moose Herd uses a stationary camera that always shows the same play area. The player remains near the bottom of the screen and can move horizontally to line up attacks. This creates a simple, readable challenge focused on positioning, timing, and accuracy.

## Gameplay

The main gameplay loop is:

1. Animals spawn at random horizontal positions near the top of the screen.
2. Each animal travels downward toward the player's side of the play area.
3. The player moves left or right along the bottom of the screen.
4. The player throws steaks upward at the approaching animals.
5. An animal disappears when it is struck by a steak.
6. The player loses if any animal moves past them and reaches the losing boundary.

The challenge is to identify the most immediate threat, move into position, and throw accurately before another animal slips past.

## Features

- Fixed-camera arcade gameplay
- Horizontal player movement along the bottom of the screen
- Randomized animal spawn positions
- Animals that continuously travel toward and past the player
- Steak-throwing projectile mechanic
- Animals disappear when hit by a steak
- Immediate loss when an animal gets past the player
- Simple survival-focused gameplay loop
- Built with Unity and C#
- Suitable for a downloadable build and a browser-playable WebGL build

## Controls

Replace the controls below if the final input bindings are different.

| Action | Control |
| --- | --- |
| Move left | `A` or Left Arrow |
| Move right | `D` or Right Arrow |
| Throw a steak | `Space` |

## How to Play

1. Launch the downloaded game or open the Unity Play version.
2. Watch the top of the screen for newly spawned animals.
3. Move left and right to line the player up with an approaching animal.
4. Throw a steak toward the animal before it reaches the bottom of the screen.
5. Continue stopping every animal for as long as possible.

You lose as soon as one animal gets past the player. Positioning matters because the camera does not move and the player can only travel sideways along the bottom of the play area.

## Installation

### Windows

1. Open the itch.io page using the link near the top of this README.
2. Download the Windows version of Moose Herd.
3. Extract the downloaded ZIP file.
4. Keep the executable, its matching `_Data` folder, and all supporting files together.
5. Run the `.exe` file to start the game.

Windows may display a warning for an unsigned application downloaded from the internet. Confirm that the build came from the official itch.io page before running it.

### macOS and Linux

If downloadable macOS or Linux builds have not been published, players on those platforms can try the browser version through Unity Play. A Windows `.exe` does not run natively on macOS or Linux.

## Playing the Web Version

The Unity Play edition runs in a compatible desktop web browser:

1. Open the Unity Play link near the top of this README.
2. Wait for the WebGL build to finish loading.
3. Click inside the game window so it receives keyboard input.
4. Use fullscreen mode if the embedded game window is too small.

A current desktop version of Chrome, Edge, or Firefox is recommended. Loading time and performance may vary depending on the browser and computer.

## Development

### Technologies Used

- Unity
- C#
- Unity Input System or keyboard input handling
- Prefabs for animals and steak projectiles
- Colliders and triggers for hit and loss detection
- Randomized spawning
- WebGL for browser publishing
- Git and GitHub for version control

### Core Systems

The game can be organized around the following systems:

- **Player controller:** Reads horizontal input, keeps the player within the visible play area, and creates steak projectiles.
- **Animal spawner:** Selects spawn positions and creates random animals near the top of the screen.
- **Animal movement:** Moves each spawned animal toward the bottom of the screen.
- **Steak projectile:** Travels away from the player and detects contact with animals.
- **Hit detection:** Removes both the animal and steak when a valid collision occurs.
- **Lose boundary:** Detects animals that have passed the player and ends the game.
- **Game manager:** Tracks whether the game is active and controls game-over or restart behavior.
- **Camera:** Remains stationary and frames the entire play area.

### Requirements

To open and modify the project, install:

- Unity Hub
- The Unity Editor version listed in `ProjectSettings/ProjectVersion.txt`
- Visual Studio, Visual Studio Code, or another C# editor
- Windows Build Support for a Windows edition
- Web Build Support for a Unity Play edition

### Opening the Project

1. Clone or download the repository.
2. Open Unity Hub.
3. Select **Add** or **Add project from disk**.
4. Choose the project's root folder.
5. Open it with the Unity Editor version recorded in `ProjectSettings/ProjectVersion.txt`.
6. Allow Unity to import the assets and recreate generated folders.
7. Open the main scene from the `Assets` directory.
8. Press the Play button to test the game.

Generated directories such as `Library`, `Temp`, `Logs`, and `obj` should not be committed to Git because Unity recreates them automatically.

## Building the Project

### Windows Build

1. Open **File > Build Profiles**.
2. Select the Windows profile and switch platforms if necessary.
3. Confirm that the main game scene is present and enabled in the scene list.
4. Select **Build**.
5. Choose an empty output folder.
6. Test the complete build before compressing it into a ZIP file for itch.io.

### Web Build and Unity Play

1. Install Web Build Support for the project's Unity Editor version through Unity Hub.
2. Open **File > Build Profiles**.
3. Add or select the Web profile.
4. Choose **Switch Platform** if Web is not already active.
5. Confirm that the correct game scene is included.
6. Select **Build and Run** to test the game in a local browser.
7. Return to Build Profiles and select **Publish to Play**.
8. Upload the build and complete the game's Unity Play page.

Test movement, steak spawning, hit detection, random animal spawning, the losing boundary, and restarting in the final Web build.

## Project Structure

A typical repository structure is:

```text
Moose-Herd/
├── Assets/                 Scenes, scripts, prefabs, models, and other assets
├── Packages/               Unity package configuration
├── ProjectSettings/        Unity project and editor settings
├── .gitignore              Generated files excluded from version control
└── README.md               Project documentation
```

Published builds do not need to be committed to the source repository. The Windows build can be distributed through itch.io, while the Web build can be hosted through Unity Play.

## Known Limitations

- The camera remains fixed throughout gameplay.
- Player movement is restricted to the horizontal axis near the bottom of the screen.
- Allowing a single animal to pass the player immediately ends the game.
- WebGL loading time and performance can vary between browsers.
- Keyboard controls are intended primarily for desktop players unless mobile or controller input is added.

## Credits

### Development

- Developed by Minsung Kim

### Assets

List every third-party model, texture, sound effect, music track, font, or Unity Asset Store package used in the game. Include the creator, source, and license when available.

Example:

```text
Asset name — Creator
Source: https://example.com
License: License name
```

## License

No license has been specified for this project yet. Unless a license file is added, the source code and original assets remain under the copyright of their respective owner and may not automatically be reused or redistributed.

Third-party assets remain subject to their original licenses.
