list(APPEND VTKExtensionsPluginAlembic_list
     TestF3DAlembicReader.cxx
    )

if(VTK_VERSION VERSION_LESS_EQUAL 9.1.0)
  cmake_policy(SET CMP0115 OLD)
endif()

vtk_add_test_cxx(VTKExtensionsPluginAlembic tests
  NO_DATA NO_VALID NO_OUTPUT
  ${VTKExtensionsPluginAlembic_list}
  ${F3D_SOURCE_DIR}/testing/ ${CMAKE_BINARY_DIR}/Testing/Temporary/)
vtk_test_cxx_executable(VTKExtensionsPluginAlembic tests)
