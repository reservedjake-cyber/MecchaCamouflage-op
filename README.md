<p align="center">
  <img
    src="assets/meccha-camouflage-banner.png"
    alt="Meccha Camouflage banner"
    width="100%"
  />
</p>

# MecchaCamouflage

Mod for [MECCHA CHAMELEON](https://store.steampowered.com/app/4704690/).

<p align="center">
  <img
    src="assets/demo.png"
    alt="Meccha Camouflage demo"
    width="100%"
  />
</p>

[Download](https://github.com/acentrist/MecchaCamouflage/releases/latest).

Extract the release zip into:

```text
C:\Program Files (x86)\Steam\steamapps\common\MECCHA CHAMELEON\Chameleon\Binaries\Win64
```

After extraction, the important files should look like this:

```text
C:\Program Files (x86)\Steam\steamapps\common\MECCHA CHAMELEON\
  Chameleon\
    Binaries\
      Win64\
        dwmapi.dll
        UE4SS.dll
        UE4SS-settings.ini
        Mods\
          mods.txt
          MecchaCamouflage\
            dlls\
              main.dll
```

PowerShell install:

```powershell
$GameRoot="C:\Program Files (x86)\Steam\steamapps\common\MECCHA CHAMELEON"; $InstallDir=Join-Path $GameRoot "Chameleon\Binaries\Win64"; $Release=Invoke-RestMethod "https://api.github.com/repos/acentrist/MecchaCamouflage/releases/latest"; $ZipUrl=($Release.assets | Where-Object { $_.name -like "*.zip" } | Select-Object -First 1).browser_download_url; $ZipPath=Join-Path $env:TEMP "meccha-camouflage.zip"; Invoke-WebRequest $ZipUrl -OutFile $ZipPath; Expand-Archive -Force $ZipPath $InstallDir
```

Command Prompt install:

```bat
powershell -NoProfile -ExecutionPolicy Bypass -Command "$GameRoot='C:\Program Files (x86)\Steam\steamapps\common\MECCHA CHAMELEON'; $InstallDir=Join-Path $GameRoot 'Chameleon\Binaries\Win64'; $Release=Invoke-RestMethod 'https://api.github.com/repos/acentrist/MecchaCamouflage/releases/latest'; $ZipUrl=($Release.assets | Where-Object { $_.name -like '*.zip' } | Select-Object -First 1).browser_download_url; $ZipPath=Join-Path $env:TEMP 'meccha-camouflage.zip'; Invoke-WebRequest $ZipUrl -OutFile $ZipPath; Expand-Archive -Force $ZipPath $InstallDir"
```

In game, aim the camera at the background you want to match, then press `F10`.

Use at your own risk.

License: [MIT](LICENSE.txt)
