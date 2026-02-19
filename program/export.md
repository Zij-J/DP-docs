# Export the Game
Document: https://docs.godotengine.org/en/stable/tutorials/export/exporting_projects.html

- [ ] 1. Add export preset: 
   - [x] Windows
   - [ ] Android
- [X] 2. Download [export templates](https://godotengine.org/download/windows/) \
    installed in `C:/Users/Zij-J/AppData/Roaming/Godot/export_templates/4.6.stable`
- [x] 3. Select unnecessary resources to be imported
  - [x] godot-git-plugin
- [x] 4. Set main scene: `res://levels/mechanism_playground.tscn`
- [ ] 5. Platform specific settings
   - [x] Windows for fun
   - [ ] Windows for real
   - [ ] Android


### Windows
Document:
https://docs.godotengine.org/en/stable/tutorials/export/exporting_for_windows.html

- [x] 1. Auto create ICO file for icons   
        Set `Project Setting/Application/Config/Icon`: `res://icon.svg`
- [ ] 2. For real: code signing
  - [x] [signtool.exe](https://learn.microsoft.com/en-us/windows/win32/seccrypto/signtool): installed with Visual Studio `C:\Program Files (x86)\Windows Kits\10\bin\10.0.22621.0\x64\signtool.exe`
  - [ ] certificate ([reddit](https://www.reddit.com/r/godot/comments/16u9kzv/is_code_signing_required_for_windows_builds_is/): [self-sign](https://learn.microsoft.com/en-us/windows/msix/package/create-certificate-package-signing) is good but still some defender warning, buy one with a few hundred $/year if needed): 
  - [ ] Set them in Godot


### Android
Document:
https://docs.godotengine.org/en/stable/tutorials/export/exporting_for_android.html

- [x] 1. [OpenJDK 17](https://adoptium.net/temurin/releases?version=17&os=any&arch=any)  
  installed in `C:\Program Files\Eclipse Adoptium\jdk-17.0.18.8-hotspot\`
- [x] 2. Android SDK  
    installed in `C:\Program Files\Android\sdk`   
    from [*sdkmanager* command line tool](https://developer.android.com/tools/sdkmanager) installed in `C:\Program Files\Android\sdk\cmdline-tools\latest`  
    Install command (in admin in `bin`):  
    ```shell
    .\sdkmanager --sdk_root="C:\Program Files\Android\sdk" "platform-tools" "build-tools;35.0.1" "platforms;android-35" "cmake;3.10.2.4988404" "ndk;28.1.13356709"
    ```
    - `"cmdline-tools;latest"` already installed, no need.
- [ ] 3.
- [ ] 