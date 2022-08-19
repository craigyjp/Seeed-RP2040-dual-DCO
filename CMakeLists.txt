cmake_minimum_required(VERSION 3.13)

include(pico_sdk_import.cmake)

project(pico-dco-seeed C CXX ASM)
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

pico_sdk_init()

add_executable(pico-dco-seeed
  pico-dco-seeed.c
  usb_descriptors.c
)

pico_generate_pio_header(pico-dco-seeed ${CMAKE_CURRENT_LIST_DIR}/pico-dco-seeed.pio)

pico_enable_stdio_usb(pico-dco-seeed 0)
pico_enable_stdio_uart(pico-dco-seeed 1)

target_include_directories(pico-dco-seeed PRIVATE ${CMAKE_CURRENT_LIST_DIR})
target_link_libraries(pico-dco-seeed PRIVATE pico_stdlib hardware_pio hardware_adc hardware_pwm tinyusb_device tinyusb_board)

target_compile_definitions(pico-dco-seeed PRIVATE
    PICO_DEFAULT_UART_RX_PIN=1
 )

pico_add_extra_outputs(pico-dco-seeed)
