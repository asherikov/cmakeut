Travis CI: https://travis-ci.org/asherikov/cmakeut [![Build Status](https://travis-ci.org/asherikov/cmakeut.svg?branch=master)](https://travis-ci.org/asherikov/cmakeut)

cmake modules:

    - cmakeut_add_external_git_project
      wrappers for ExternalProject_Add(), allow compilation without
      Internet connection.

    - cmakeut_copy_dir_if_exists
    - cmakeut_copy_file_if_exists
      add custom targets to copy directories or files if they exists.

    - cmakeut_dump_variables
      dump all cmake variables (for debugging)

    - cmakeut_list_filenames
      list filenames in the given directory

    - cmakeut_detect_func_macro
      detect __func__ and __FUNCTION__

    - cmakeut_add_cpp_test
      cmake test wrapper

    - third party
        - FindEigen3.cmake
          find Eigen headers, copied from Eigen distribution
