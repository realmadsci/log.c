cmake_minimum_required(VERSION 3.13 FATAL_ERROR)

option(LOG_USE_COLOR "log use color" ON)

add_library(log "")
target_sources(log
	PRIVATE
		src/log.c
		src/log.h
	PUBLIC
		src/log.h
)

if(LOG_USE_COLOR)
	target_compile_definitions(log
		PRIVATE
			LOG_USE_COLOR
	)
endif()

target_include_directories(log 
	INTERFACE 
		"${CMAKE_CURRENT_LIST_DIR}/src"
)