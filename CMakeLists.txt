set(PROJECT rpi_i2c_gyro)

cmake_minimum_required(VERSION 3.13)
include($ENV{PICO_SDK_PATH}/external/pico_sdk_import.cmake)

project(rpi_i2c_gyro C CXX ASM)

pico_sdk_init()

add_executable(rpi_i2c_gyro
        mpu6050_i2c.cpp
        )


# pull in common dependencies and additional i2c hardware support
target_link_libraries(rpi_i2c_gyro pico_stdlib hardware_i2c pico_stdio_usb)

pico_enable_stdio_usb(rpi_i2c_gyro 1)

# create map/bin/hex file etc.
pico_add_extra_outputs(rpi_i2c_gyro)
