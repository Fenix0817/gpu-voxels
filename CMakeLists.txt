CMAKE_MINIMUM_REQUIRED(VERSION 2.8)

SET(ICMAKER_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/icmaker)

IF(EXISTS ${ICMAKER_DIRECTORY}/IcMaker.cmake)
  INCLUDE(${ICMAKER_DIRECTORY}/IcMaker.cmake)
ELSE()
  INCLUDE(${ICMAKER_DIRECTORY}/CMakeLists.txt)
ENDIF()

ADD_SUBDIRECTORY(${CMAKE_SOURCE_DIR}/packages)
ADD_SUBDIRECTORY(${CMAKE_SOURCE_DIR}/doc)

IF (EXISTS "${CMAKE_SOURCE_DIR}/script" AND IS_DIRECTORY "${CMAKE_SOURCE_DIR}/script")
  ADD_SUBDIRECTORY(${CMAKE_SOURCE_DIR}/script)
ENDIF ()
