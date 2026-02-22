# Export the Game
Document: https://docs.godotengine.org/en/stable/tutorials/export/exporting_projects.html

- [ ] 1. Add export preset: 
   - [x] Windows
   - [ ] Android
- [X] 2. Download [export templates](https://godotengine.org/download/windows/) \
    installed in `C:/Users/Zij-J/AppData/Roaming/Godot/export_templates/4.6.stable`
- [x] 3. Set main scene: `res://levels/mechanism_playground.tscn`
- [ ] 4. Platform specific settings
   - [x] Windows for fun
   - [ ] Windows for real
   - [x] Android for fun
   - [ ] Android for real


### Windows
Document:
https://docs.godotengine.org/en/stable/tutorials/export/exporting_for_windows.html

- [x] 1. Auto create ICO file for icons   
        Set `Project Setting/Application/Config/Icon`: `res://icon.svg`
- [x] 2. Select unnecessary resources to be imported
  - [x] godot-git-plugin
- [ ] 3. For real: code signing
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
- [x] 3. Open `Project Setting/rendering/textures/vram_compression/import_etc2_astc` and delete-regenerate `.godot/imported` folder
- [x] 4. Select unnecessary resources to be imported
  - [x] godot-git-plugin
- [x] 5. Set `package/signed` to ture in export options (Otherwise my installation will fail)
- [x] 6. If `The project name does not meet ...`, change `package/unique_name`.

Setting up *one-click deploy* (no *drop the apk to phone's folder needed*):  
https://docs.godotengine.org/en/stable/tutorials/export/one-click_deploy.html#one-click-deploy
- [x] 7. Add `C:\Program Files\Android\sdk\platform-tools` to path, which unlocks `adb`   
- [x] 8. In phone: Enable developer mode > enable USB debugging > Plug usb in
- [x] (9. `adb devices` to ensure the phone is connected.) 
- [ ] 10. For real: launcher icons
- [ ] 11. For real: Google Play Store
- [ ] 12. For real: Optimizing the file size
