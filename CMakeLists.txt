cmake_minimum_required(VERSION 2.6)
project(parlent)

set(CMAKE_AUTOMOC ON)
set(CMAKE_INCLUDE_CURRENT_DIR ON)

set(CMAKE_CXX_FLAGS "-std=c++11 -Wall -Werror")

set(SOURCE
    ${SOURCE}
    src/main.cpp
    src/dataframe.cpp
    src/device.cpp
    src/psh_modem.cpp
    )
    
set(HEADERS
    ${HEADERS}
    src/dataframe.h
    src/device.h
    src/modem.h
    src/psh_modem.h
    )

add_executable(parlent ${SOURCE} ${HEADERS})

target_link_libraries(parlent asound fftw3)

install(TARGETS parlent RUNTIME DESTINATION bin)
