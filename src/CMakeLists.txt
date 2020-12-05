add_library(libexample SHARED "")

target_sources(
    libexample
    PRIVATE
        exp1.cpp
        ${CMAKE_CURRENT_LIST_DIR}/exp1.h # optional
    )

target_include_directories(
    libexample
    PUBLIC
        ${CMAKE_CURRENT_LIST_DIR}
    )

# respective macro definitions
message("CMAKE_BUILD_TYPE = ${CMAKE_BUILD_TYPE}")
if(CMAKE_BUILD_TYPE MATCHES Debug)
    target_compile_definitions(libexample PUBLIC _DEBUG)
elseif(CMAKE_BUILD_TYPE MATCHES Release)
else()
endif()

