cmake_minimum_required(VERSION 3.13 FATAL_ERROR)

add_library(log "")
target_sources(log
	PRIVATE
		src/log.c
		src/log.h
	PUBLIC
		src/log.h
)

target_include_directories(log 
	INTERFACE 
		"${CMAKE_CURRENT_LIST_DIR}/src"
)