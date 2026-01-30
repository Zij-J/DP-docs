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
