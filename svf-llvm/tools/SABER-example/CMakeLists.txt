if(DEFINED IN_SOURCE_BUILD)
  add_llvm_tool(saber-ex saber.cpp)
else()
  add_executable(saber-ex saber.cpp)

  target_link_libraries(saber-ex SvfLLVM ${llvm_libs})

  set_target_properties(saber-ex PROPERTIES RUNTIME_OUTPUT_DIRECTORY
                                         ${CMAKE_BINARY_DIR}/bin)
endif()
