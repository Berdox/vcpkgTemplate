# vcpkgTemplate
  A barebone template of an vcpkg manger and cmake project with an exmaple of fmt package built in  
## Instructions  
  1. Make an out/build directory in project  
  2. cd into the directory  
  3. Run the command `cmake ../../.` wait until it is done  
  4. Run the build system you want to use or have installed  
    - Ex. for unix/linux you can use the make build system so you can just run the command `make` and it will build the project
## Adding Packages
  - To add a vcpkg package you need to add it to the dependencies list in the vcpkg.json file
  - Then you have to modify the CMakeLists.txt file and add `find_package([package name] CONFIG REQUIRED)` and `target_link_libraries(vcpkgTemplate PRIVATE [package name])` when vcpkg installs the package it will tell you exactly what to put in the CMakeList.txt
