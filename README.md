# Onethinx Core Linux dependencies pack

## How to setup Visual Studio Code with the Onethinx Core dependencies pack
 The instructions on how to update are way down below.

## 1. Download prerequisites
- **VS Code**
    - [Download Visual Studio Code](https://code.visualstudio.com/download)
- **Onethinx Dependencies Pack**
    - [Download the Onethinx dependencies pack for Linux](https://github.com/onethinx/VSCode_OnethinxPack_Linux/archive/refs/heads/main.zip)
- **CMake**
    - Install CMake: `sudo apt install cmake`
## 2. Install VS Code & extensions
  - Install VS Code.
  - Install extensions:
    - ARM Assembly Support For Visual Studio Code (dan-c-underwood)
    - C/C++ IntelliSense, debugging (microsoft)
    - CMake language support (twxs)
    - CMake Tools (microsoft)
    - Cortex-Debug GDB support (marus25)
    - Output Colorizer (IBM)
    - Power Tools (e.GO Mobile)
    - Tasks (actboy168)
  - Apply the OpenOCD USB rules by running `yourpath/VSCode_OnethinxPack_Linux/tools_3.0/linux/openocd/udev_rules/install_rules.sh`.
## 3. Install the Onethinx Dependencies Pack
  - Unzip the pack archive to your local harddisk (eg: /Applications/VSCode_OnethinxPack_Linux).<br>
    - Hint: you might want to remove '-main' at the end of the folder name.
  - Open ~.profile: Terminal >> `cd ~ && nano .profile`<br>
     or when using Bash shell:<br>
     open ~.bash_profile: Terminal >> `cd ~ && nano .bash_profile`
  - Add this to the end of the file (make sure you enter the correct path) and save:
    ```
    # Loading environment variables for the Onethinx Pack
    export ONETHINX_PACK_LOC="/yourpath/VSCode_OnethinxPack_Linux"
    source "$ONETHINX_PACK_LOC/variables.env"
    ```
  - Restart your machine (or log-out and log-in) to reload the environment variables.
## 4. Check
  - If CMake, Make and the compiler is correctly installed by typing the following into your terminal or terminal window of VS Code.
    - `cmake -version`
    - `make -v`
    - `arm-none-eabi-gcc -v`
  - If you have not done this yet, download the [Hello World Project](https://github.com/onethinx/VSCode_HelloWorld)
    - You should be able to build and debug this project. If you experience issues, [your feedback is appreciated.](https://github.com/onethinx/VSCode_OnethinxPack_Linux/issues)
## 5. Remind
  - After changing the device configuration (or project file structure) to use
    - Clean Reconfigure
    - Clean Rebuild
       in order to build the image properly  
  - To delete the contents of the build folder
    - if you copied the project including build folder from another location / machine
    - when build fails.
## How to update
  - Download the [latest Onethinx Dependencies Pack](https://github.com/onethinx/VSCode_OnethinxPack_Linux/archive/refs/heads/main.zip)
  - Delete the contents of the Dependencies Pack folder from you harddisk
  - Unpack the contents of the archive to the Dependencies Pack folder
  - Make sure the correct path is set in the environment variables (see step 3)
  - Restart your machine (or log-out and log-in) to reload the environment variables.
