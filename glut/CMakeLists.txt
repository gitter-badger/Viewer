PROJECT(RVIEW_GLUT)

LINK_LIBRARIES(rview++ registration++ transformation++ image++ geometry++
common++ recipes) 

INCLUDE (${CMAKE_ROOT}/Modules/FindGLUT.cmake)

IF (GLUT_INCLUDE_PATH)
  INCLUDE_DIRECTORIES(${GLUT_INCLUDE_PATH})
ENDIF(GLUT_INCLUDE_PATH)

IF (GLUT_LIBRARY)
  LINK_LIBRARIES (${GLUT_LIBRARY})
ENDIF (GLUT_LIBRARY)

INCLUDE (${CMAKE_ROOT}/Modules/FindOpenGL.cmake)

IF (GLU_LIBRARY)
   LINK_LIBRARIES (${GLU_LIBRARY})
ENDIF (GLU_LIBRARY)
 
IF (OPENGL_INCLUDE_PATH)
  INCLUDE_DIRECTORIES(${OPENGL_INCLUDE_PATH})
ENDIF(OPENGL_INCLUDE_PATH)

IF (OPENGL_LIBRARY)
  LINK_LIBRARIES (${OPENGL_LIBRARY})
ENDIF (OPENGL_LIBRARY)

SET(GLUT_SRCS main.cc)

irtk_add_executable(display ${GLUT_SRCS})
INSTALL_TARGETS(/bin display)