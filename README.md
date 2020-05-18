# A simple CubeMx project with CMakeLists

This little repository helps me getting started with CMake and CubeMx tools in my personal projects. 
Many thanks to github user @ObKo for making this possible!

### To compile you need to specify:
#### Windows example:
* TOOLCHAIN_PREFIX (a path to ARM Embedded compiler) e.g you can use toolchain from ChibiStudio. 
  
  `C:/ChibiStudio/tools/GNU Tools ARM Embedded/9.0 2019q4/`

* STM32_FAMILY e.g. `F4`
* STM32_CHIP e.g. `STM32F411xE`
* STM32Cube_DIR
  * if libraries are copied into project folder then link to project root path:
  `C:/Users/xxx/Documents/DEV/BlinkyF411`
  * if libreries are not copied then put a path to CubeMX repository. The  path should link to CubeMx repository: e.g.
  `C:/Users/xxx/STM32Cube/Repository/STM32Cube_FW_F4_V1.25.0` 

* CMAKE_BUILD_TYPE - `Debug` or `Release`
* CMAKE_TOOLCHAIN_FILE - a path to toolchain file. Get it from [this repository](https://github.com/ObKo/stm32-cmake) and link to the `gcc_stm32.cmake`.

#### Linux example:
`cmake -DTOOLCHAIN_PREFIX="/home/chibios/ChibiStudio/tools/GNU Tools ARM Embedded/9.2.1 2019q4/" -DSTM32_FAMILY=F4 -DSTM32_CHIP=STM32F411xE -DSTM32Cube_DIR=. -DCMAKE_BUILD_TYPE=Debug -DCMAKE_TOOLCHAIN_FILE=../../stm32-cmake/cmake/gcc_stm32.cmake ..`

### What if I want to generate/adapt project for a different target?:
1. Generate CubeMx project as `Makefile project`
2. Copy CMakeLists.txt into root folder
3. Update it with yours source files
4. Use Cmake with specified settings 