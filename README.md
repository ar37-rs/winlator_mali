<p align="center">
	<img src="logo.png" width="376" height="128" alt="Winlator Logo" />  
</p>

# Winlator 10.0 hotfix modified and added some tweaks for Mali GPUs

### Signed with different signature, uninstall the original one before installing the mali version.

### Winulator vrigl config (any Mali-G52 GPU and Up)
* Add ENVIRONMENT VARIABLE

   ```MESA_GLSL_VERSION_OVERRIDE``` set value to ```410```,  ```150``` or ```140``` (choose which best accordingly)
   
* Graphics Driver set to VirGL
* DX Wrapper set to WineD3D
  
### Winulator vortex + WineD3D config (supported minimum Mali-G52 GPU with driver version 49.x or Mali-G57 and Up)
* Add ENVIRONMENT VARIABLES (choose which best accordingly)
      
   For OpenGL 3.2:
   
   ```MESA_GL_VERSION_OVERRIDE``` set value to ```3.2COMPAT```
   
   ```MESA_GLSL_VERSION_OVERRIDE``` set value to ```150```
    
   For OpenGL 4.1:
   
   ```MESA_GL_VERSION_OVERRIDE``` set value to ```4.1COMPAT```
   
   ```MESA_GLSL_VERSION_OVERRIDE``` set value to ```410```
        
* Graphics Driver set to Vortex (Universal)
* DX Wrapper set to WineD3D

### Winulator vortex + DXVK config (supported minimum Mali-G52 GPU with driver version 49.x or Mali-G57 and Up)
* Graphics Driver set to Vortex (Universal)
* Vortex Configure:
  
   Vulkan version (choose accordingly)

   Max Device Memory (set accordingly)
  
   Exposed Extensions (unchecklist the ```VK_EXT_extended_dynamic_state``` to fix the missing textures in some games for some Mali drivers)
  
* DX Wrapper set to DXVK
* Disable WineD3D on wine

   Start Menu -> WineD3D_Renderer -> Disable.bat (fix crash in some games)

   and then restart wine

### Add recommended settings to ENVIRONMENT VARIABLES:
   
   ```mesa_glthread``` turn off for stability
  
   ```BOX64_MMAP32``` set value to ```1```
  
   ```BOX64_SAFEFLAGS``` set value to ```2```

   ```WINEDEBUG``` set value to ```-all```

# Wine config
* Choose suitable version of wined3d accordingly (each game/app may require different version)
* OffScreenRendering mode:
  
  Using Backbuffer:
  
  Rendering -> Backbuffer.bat (fix blackscreen on some devices)

  Using FramebufferOBject:
  
  Rendering -> FBO.bat (default)


Based on and thanks to:

https://github.com/ajay9634/winlator-ajay

https://github.com/Fcharan/WinlatorMali


----

[![Play on Youtube](https://img.youtube.com/vi/ETYDgKz4jBQ/3.jpg)](https://www.youtube.com/watch?v=ETYDgKz4jBQ)
[![Play on Youtube](https://img.youtube.com/vi/9E4wnKf2OsI/2.jpg)](https://www.youtube.com/watch?v=9E4wnKf2OsI)
[![Play on Youtube](https://img.youtube.com/vi/czEn4uT3Ja8/2.jpg)](https://www.youtube.com/watch?v=czEn4uT3Ja8)
[![Play on Youtube](https://img.youtube.com/vi/eD36nxfT_Z0/2.jpg)](https://www.youtube.com/watch?v=eD36nxfT_Z0)

----

# Useful Tips

- If you are experiencing performance issues, try changing the Box64 preset to `Performance` in Container Settings -> Advanced Tab.
- For applications that use .NET Framework, try installing `Wine Mono` found in Start Menu -> System Tools -> Installers.
- If some older games don't open, try adding the environment variable `MESA_EXTENSION_MAX_YEAR=2003` in Container Settings -> Environment Variables.
- Try running the games using the shortcut on the Winlator home screen, there you can define individual settings for each game.
- To display low resolution games correctly, try to enabling the `Force Fullscreen` option in the shortcut settings.
- To improve stability in games that uses Unity Engine, try changing the Box64 preset to `Stability` or in the shortcut settings add the exec argument `-force-gfx-direct`.

# Information

This project has been in constant development since version 1.0, the current app source code is up to version 7.1, I do not update this repository frequently precisely to avoid unofficial releases before the official releases of Winlator.

# Credits and Third-party apps
- GLIBC Patches by [Termux Pacman](https://github.com/termux-pacman/glibc-packages)
- Wine ([winehq.org](https://www.winehq.org/))
- Box86/Box64 by [ptitseb](https://github.com/ptitSeb)
- Mesa (Turnip/Zink/VirGL) ([mesa3d.org](https://www.mesa3d.org))
- DXVK ([github.com/doitsujin/dxvk](https://github.com/doitsujin/dxvk))
- VKD3D ([gitlab.winehq.org/wine/vkd3d](https://gitlab.winehq.org/wine/vkd3d))
- D8VK ([github.com/AlpyneDreams/d8vk](https://github.com/AlpyneDreams/d8vk))
- CNC DDraw ([github.com/FunkyFr3sh/cnc-ddraw](https://github.com/FunkyFr3sh/cnc-ddraw))
- Ubuntu RootFs ([Focal Fossa](https://releases.ubuntu.com/focal))
- PRoot ([proot-me.github.io](https://proot-me.github.io))

Many thanks to [ptitSeb](https://github.com/ptitSeb), [Danylo](https://blogs.igalia.com/dpiliaiev/tags/mesa/), [Max Ivan](https://github.com/Maxython), [Twaik Yont](https://github.com/twaik), [alexvorxx](https://github.com/alexvorxx) and others.<br>
Thank you to all the people who believe in this project.
