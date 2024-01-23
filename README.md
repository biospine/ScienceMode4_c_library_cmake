
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