# 3dprint-ender3-marlin
3D-printer Creality Ender 3 firmware & configuration project

This project is used for tracking changes in my Creality Ender 3  3D printer

3D-printer:
- Creality Ender-3 (https://www.creality.com/products/ender-3-3d-printer)
- Creality V4.2.7 Silent Board TMC2225 Driver (https://www.creality3dofficial.com/products/creality-silent-mainboard-v4-2-7)
- BL Touch Auto Leveling Kit (https://www.creality.com/products/bl-touch-auto-leveling-kit)

SW:
- Marlin v2.x (https://marlinfw.org/)
- Platform IO VSCode  (https://platformio.org/install/ide?install=vscode)
  
Related links:
- Redit building marlin firmware for creality 427 (https://www.reddit.com/r/ender5/comments/lkmku7/building_marlin_firmware_for_creality_427/)


## Version 1.0  (01.01.2024)
- based on Marlin-2.1.2.2
- add BL-Touch support
  
  
## How to build manualy

Prerequisities:
 - instaled git (https://git-scm.com/downloads)
 - instaled platform.io (https://platformio.org/install/ide?install=vscode)
 - be sure you don´t change the line endings in original files 
  ```bash git config core.autocrlf false```

1. Clone my github repository
   
   ```bash
   git clone git@github.com:keklabs/3dprint-ender3-marlin.git
   #switch the working directory
   cd 3dprint-ender3-marlin
  ```
2. Marlin repository was added as a git submodule in in the "Marlin" subdirectory (you don´t need this, skip it)
    You are in Working Directory: 
    ```bash
    git submodule add https://github.com/MarlinFirmware/Marlin.git marlin
    ```
3. Checkout the desired Marlin release tag
  ```bash
  cd marlin
  # Fetch all tags from the remote repository
  git fetch --tags
  # Checkout the specific release tag, e.g., 2.1.2.2, and create a local branch for it
  git checkout tags/2.1.2.2 -b release-2.1.2.2
  ```
4. Commit the submodule reference in your main repository
  ```bash
  cd ..
  # Stage the submodule directory update
  git add marlin
  # Commit with an English commit message
  git commit -m "Add Marlin submodule at release 2.1.2.2"
  ```

5. Same for config examples
  ```bash
  git submodule add -b release-2.1.2 https://github.com/MarlinFirmware/Configurations.git marlin-configurations
  cd marlin-configurations
  git fetch --tags
  git checkout tags/2.1.2.2 -b release-2.1.2.2
  cd ..
  git add marlin-configurations
  git commit -m "Add Configurations submodule from branch release-2.1.2.2"
  ```

6. Update submodules for new releases
  ```bash
  cd marlin
  git fetch --tags
  # Checkout the new tag, e.g., 2.1.2.3, and create/update your branch if needed
  git checkout tags/2.1.2.3 -b release-2.1.2.3
  cd ..
  git add marlin
  git commit -m "Update Marlin submodule to release 2.1.2.3"

  cd marlin-configurations
  git fetch --tags
  # Checkout the new tag, e.g., 2.1.2.3, and create/update your branch if needed
  git checkout tags/2.1.2.3 -b release-2.1.2.3
  cd ..
  git add marlin-configurations
  git commit -m "Update Marlin Configurations submodule to release 2.1.2.3"
  ```

