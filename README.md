# eduke32
works for Fury 1.00 but not with the newest 1.02 from Steam or GOG

# build under windows10 for switch
1. devkitpro with switch support from https://github.com/devkitPro/installer/releases
2. start devkitPro->Msys2 Shell and add env variable to /etc/bash.bashrc

   ```echo 'export DEVKITA64="/opt/devkitpro/devkitA64"' >> /etc/bash.bashrc```
2. restart devkitPro->Msys2 Shell and install libs for eduke32 
   
   ```pacman -S switch-sdl2 switch-libvpx switch-sdl2_mixer switch-pkg-config switch-libvorbis gcc liblz4-devel zlib-devel```
3. Clone switch-tools for nacptool
    
   ```git clone https://github.com/switchbrew/switch-tools.git```
4. Build switch-tools and install nacptool.exe
   ```cd switch-tools
   . autogen.sh
   ./configure
   make
   make install```
   
3. Go into cloned eduke32 folder
4. Build eduke32, standard version for switch

   ```make PLATFORM=SWITCH
   make PLATFORM=SWITCH clean```
5. Build eduke32, Ion Fury version for switch, you can clean the folder after build.

   ```make PLATFORM=SWITCH FURY=1
   make PLATFORM=SWITCH clean```
6. You will find fury.nro and eduke32.nro in eduke32 folder for further usage 
