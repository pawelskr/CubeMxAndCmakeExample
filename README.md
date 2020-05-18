# A simple CubeMx project with CmakeLists

### To compile you need to specify:
* TOOLCHAIN_PREFIX (a path to ARM Embedded compiler) e.g you can use toolchain from ChibiStudio. 
  
  `C:/ChibiStudio/tools/GNU Tools ARM Embedded/9.0 2019q4/`

* STM32_FAMILY e.g. `F4`
* STM32_CHIP e.g. `STM32F411xE`
* STM32Cube_DIR
  * if libraries are copied into project folder then:
 `C:/Users/Pawel_HO/Documents/DEV/BlinkyF411`
  * if libreries are not copied then put a path to CubeMX repository. The default path should be:
  `C:/Users/xxxx/STM32Cube/Repository/STM32Cube_FW_F4_V1.25.0` 

* CMAKE_BUILD_TYPE - `Debug` or `Release`
* CMAKE_TOOLCHAIN_FILE - a path to toolchain file. Get it from [this repository](https://github.com/ObKo/stm32-cmake)

### What if I want to generate/adapt project for a different target?:
1. Generate CubeMx project as `Makefile project`
2. Copy CMakeLists.txt into root folder
3. Update it with your source files
4. Run Cmake with specified settings 