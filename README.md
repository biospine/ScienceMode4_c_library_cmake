# ScienceMode4_c_library_cmake
`ScienceMode4_c_library_cmake` is a wrapping around the [original C library of the ScienceMode 4 protocol](https://github.com/ScienceMode/ScienceMode4_c_library) so it may be build using CMake instead of qmake. This repository was created to avoid using Qt if a super project uses CMake. It is not the most elegant solution and likely has different compiler flags to the original project.
### Build and compile project
```powershell
git clone --recurse-submodules https://github.com/biospine/ScienceMode4_c_library_cmake
mkdir build
cd build
cmake -G "Visual Studio 16 2019" -A x64 -DCMAKE_BUILD_TYPE=Release ..
cmake --build . --config Release
```

### Run unit tests (broken for now)
```powershell
cd build
ctest -C Release
```

## Install
Use component '--component smpt-library' if there are other components (e.g., from future submodules) you don't want installed.
```powershell
cmake --install . --prefix="..\install"
```
Then make sure CMake can find it.
The following PATH method works using powershell on Windows platforms. There are [many](https://cmake.org/cmake/help/latest/command/find_package.html#config-mode-search-procedure) other way to let CMake find the package.
```
cd path_to_ScienceMode4_c_library_cmake
$smpt_path = ";" + $PWD + "\install"
$env:Path = [System.Environment]::GetEnvironmentVariable("Path","Machine")
[Environment]::SetEnvironmentVariable("PATH", $env:PATH + $smpt_path, [EnvironmentVariableTarget]::Machine)
```

## How to use in another CMake project (i.e., link against)

```CMake
...

find_package(ScienceModeProtocol REQUIRED PATHS path_to_ScienceModeProtocol/install)
...

target_link_libraries(new_exe ScienceModeProtocol::sciencemode_protocol)

# Depending on install and linking methods used.
get_target_property(LIBB_LOCATION ScienceModeProtocol::sciencemode_protocol IMPORTED_LOCATION_RELEASE)
install(FILES
  ${LIBB_LOCATION}
  DESTINATION bin
)
```