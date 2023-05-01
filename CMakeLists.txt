cmake_minimum_required(VERSION 3.15)

project(STM32_Freertos_CubeMX LANGUAGES C CXX ASM)

find_bsp(
	ID com.sysprogs.project_importers.stm32.cubemx
	SOURCE_PROJECT STM32_Freertos_CubeMX.ioc
	CONFIGURATION com.sysprogs.toolchainoptions.arm.syscallspecs=--specs=rdimon.specs)

add_bsp_based_executable(
	NAME STM32_Freertos_CubeMX
	GENERATE_BIN
	GENERATE_MAP)

target_include_directories(STM32_Freertos_CubeMX PRIVATE Middlewares/Third_Party/FreeRTOS/Source/CMSIS_RTOS_V2 Middlewares/Third_Party/FreeRTOS/Source/include Middlewares/Third_Party/FreeRTOS/Source/portable/GCC/ARM_CM7/r0p1)
