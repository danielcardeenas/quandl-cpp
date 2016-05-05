# Comeback in one week when this lib is ready

## Quandl-cpp
C++ API for Quandl

Quick example:
```cpp
    #include <quandl/quandl.h>
    using quandl = leind::quandl::core;
    
    int main(int argc, char** argv) {
        quandl q;
        q.auth("qsow3FdWs24kyR56EDSy"); // Optional
        auto json = q.request("WIKI/FB");
    }
    
```

### Usage
Inside your project clone the repo this way.

```shell
git clone --recursive git@github.com:danielcardeenas/quandl-cpp.git
```

Next, add this subdirectory to your CMakeLists.txt before declaring any targets that might use it:

```cmake
# Compile library 
add_subdirectory(quandl-cpp)
```

This will create the following CMake variables which you can use in any part of your project
+ `QUANDLCPP_INCLUDE_DIR` (quandlcpp .h files)
+ `JSON_INCLUDE_DIRS` (json .h files)
+ `CPR_INCLUDE_DIRS` (cpr .h files)
+ `CPR_LIBRARIES` (cpr library)
+ `QUANDLCPP_LIB` (quandlcpp library)

```cmake
# Include directories
include_directories(${QUANDLCPP_INCLUDE_DIR} ${CPR_INCLUDE_DIRS} ${JSON_INCLUDE_DIRS})

add_executable(..)

target_link_libraries(example quandlcpp ${QUANDLCPP_LIB} ${CPR_LIBRARIES})
```
