
INCLUDE(TribitsAddExecutableAndTest)

INCLUDE_DIRECTORIES(${CMAKE_SOURCE_DIR})

TRIBITS_ADD_EXECUTABLE_AND_TEST(
  test_fibers
  SOURCES main.cpp
  ARGS -c
  NUM_MPI_PROCS 2
  COMM serial mpi
)

TRIBITS_COPY_FILES_TO_BINARY_DIR(data_heart_test_fibers_data
  SOURCE_FILES dataSingleVentricle dataXVentSingle dataSingleVentConv
  singleVentricle.mesh xVentSingle.mesh biVentCoarse.mesh
  biVentCoarsePatches.mesh biVentMediumPatches.mesh biVentMedium.mesh
  biVentFine.mesh singleVentConv.mesh siVent.mesh heartVCoa.mesh
  heartVVCoa.mesh heartVVVCoa.mesh heartMed.mesh heartVVCoaPatch.mesh
  heartVCoaPatch.mesh heartCoaTr.mesh heartMedTr.mesh heart80k.mesh
  SOURCE_DIR ${CMAKE_CURRENT_SOURCE_DIR}
)

TRIBITS_COPY_FILES_TO_BINARY_DIR(data_heart_test_fibers_data
  CREATE_SYMLINK
  SOURCE_FILES data
  SOURCE_DIR ${CMAKE_CURRENT_SOURCE_DIR}
)

TRIBITS_COPY_FILES_TO_BINARY_DIR(dataBiVent
  CREATE_SYMLINK
  SOURCE_FILES dataBiVent
  SOURCE_DIR ${CMAKE_CURRENT_SOURCE_DIR}
)

TRIBITS_COPY_FILES_TO_BINARY_DIR(dataHeart
CREATE_SYMLINK
SOURCE_FILES dataHeart
SOURCE_DIR ${CMAKE_CURRENT_SOURCE_DIR}
)

TRIBITS_COPY_FILES_TO_BINARY_DIR(dataHeartPatch
CREATE_SYMLINK
SOURCE_FILES dataHeartPatch
SOURCE_DIR ${CMAKE_CURRENT_SOURCE_DIR}
)

TRIBITS_COPY_FILES_TO_BINARY_DIR(dataSiVent
  CREATE_SYMLINK
  SOURCE_FILES dataSiVent
  SOURCE_DIR ${CMAKE_CURRENT_SOURCE_DIR}
)

#TRIBITS_COPY_FILES_TO_BINARY_DIR(fibers_test_fibers
#  SOURCE_FILES ellipsoid_fibers
#  SOURCE_DIR ${CMAKE_SOURCE_DIR}/lifev/electrophysiology/data/fibers/
#)
