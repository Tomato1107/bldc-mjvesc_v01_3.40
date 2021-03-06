This is the source code for the MJVESC DC/BLDC/FOC controller. This is originated from http://vesc-project.com/.
More detail description for MJVESC is at https://drcl.mju.ac.kr/research/mjvesc-framework

## bldc-mjvesc_v01_3.40

### I strongly recommend to use ubuntu 16.04.5 LTS.

## 1. Build GNU-ARM at Terminal - Easy way but no gui, 2019-02-08
1. add repository and update

   `sudo add-apt-repository ppa:team-gcc-arm-embedded/ppa`
   
   `sudo apt-get update`

2. install toolchain and dependencies
      
   `sudo apt-get install gcc-arm-embedded`
   
   `sudo apt-get install build-essential openocd git libudev-dev libqt5serialport5-dev`

3. build and run test at source code folder

   `make upload`


## 2-1. eclipse setting @ ubuntu, 2019-02-08
1. install jdk

    @ JDK 8
    
    `sudo add-apt-repository ppa:webupd8team/java`
    
    `sudo apt update`
    
    `sudo apt install oracle-java8-installer`
    
    @ JDK 11

    `sudo add-apt-repository ppa:linuxuprising/java`

    `sudo apt update`
    
    `sudo apt install openjdk-11-jdk`

2. install eclipse

   https://www.eclipse.org/downloads/

3. install 'gnu-arm-mcu' plugin at help -> eclipse market place

4. go to 'Packs' perspective, click refresh and install STMicroelectronics->Keil->STM32F4xx_DFP

@ Easy way - Using xpm (not recommended)

5. install nodejs, npm

    `sudo apt-get install nodejs-dev node-gyp libssl1.0-dev`
    
    `sudo apt-get install npm`

6. install xpm

    `sudo npm install --global xpm`
    
7. install ARM toolchain

    `xpm install --global @gnu-mcu-eclipse/arm-none-eabi-gcc`
    
8. install openocd

    `xpm install --global @gnu-mcu-eclipse/openocd`
   
@ Using 'gcc-arm-embedded' and 'openocd' (personally recommended)

5. just set path in eclipse 

    windows->preference->MCU
     
        Global Openocd Path -> /usr/bin
   
   done     
        

## 2-2. eclipse setting @ windows, 2019-02-08
1. install jdk

   https://www.oracle.com/technetwork/java/javase/downloads/index.html

2. install eclipse

   https://www.eclipse.org/downloads/

3. install 'gnu-arm-mcu' plugin at help -> eclipse market place

4. go to 'Packs' perspective, click refresh and install STMicroelectronics->Keil->STM32F4xx_DFP

5. install nodejs, npm

    https://nodejs.org/en/download/

6. install xpm

    `npm install --global xpm`
    
7. install ARM toolchain

    `xpm install --global @gnu-mcu-eclipse/arm-none-eabi-gcc`
    
8. install openocd

    `xpm install --global @gnu-mcu-eclipse/openocd`
    
9. install windows build tools

    `xpm install --global @gnu-mcu-eclipse/windows-build-tools`
    
    
    
## 2-3. eclipse build&run Test
1. open eclipse

2. file -> import -> c/c++ -> Existing Code as Makefile Project

3. Browse and select target folder, and set 'Toolchain for Indexer Setting' -> 'Arm Cross GCC'

4. right click at project folder imported, select properties

5. C/C++ Build -> Settings -> Devices, Select Devices -> STMicroelectronics -> STM32F4 Series -> STM32F407 (in case of mjvesc) -> Apply

6. right click at project folder imported, select build project

7. right click at project folder imported, select Run As -> Run Configuration

8. double click 'GDB OpenOCD Debugging'

9. select tab 'Debugger' and type below at 'Config options'

   `-f board/stm32f4discovery.cfg`
   
10. Click Run

## License
The software is released under the GNU General Public License version 3.0
