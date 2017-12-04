#minimum version required
cmake_minimum_required(VERSION 2.8.14)

#add project
project(examples)


#sources
file(GLOB SOURCES src/testing.cpp
				  src/Hello_triangle.cpp
				  src/Shaders.cpp	    
				  src/Shader_with_class.cpp	)
set(SOURCE_LIST ${SOURCES})
list(LENGTH SOURCE_LIST SOURCE_LENGTH)
math(EXPR  ITERATE "${SOURCE_LENGTH} -1")

#set projectname
set(PROJECT_NAMES "testing;hello_triangle;Shaders;Shaders_b")

#message(STATUS "sources are ${SOURCES}" )
#message(STATUS "projects are ${PROJECT_NAMES}" )

foreach(val RANGE ${ITERATE})
  list(GET SOURCE_LIST ${val} val1)
  list(GET PROJECT_NAMES ${val} val2)
  message(STATUS "project: ${val2}, source: ${val1}")
  add_executable(${val2} ${val1})
 

 target_link_libraries( ${val2}
					   lib::glfw
					   lib::glad)
   if(${val2} STREQUAL "Shaders_b")
	message(STATUS "found project ${val2}" ${CMAKE_CURRENT_SOURCE_DIR}/include)
	target_include_directories(${val2} PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/include}) 

  endif()
 
endforeach()




