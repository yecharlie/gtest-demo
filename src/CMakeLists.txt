add_library(libexample SHARED "")

target_sources(
    libexample
    PRIVATE
        exp1.cpp
    PUBLIC # optional
        ${CMAKE_CURRENT_LIST_DIR}/exp1.h
    )

target_include_directories(
    libexample
    PUBLIC
        ${CMAKE_CURRENT_LIST_DIR}
    )
