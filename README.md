# Quandl for C++
Simple yet powerful way to make request to Quandl API.

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

##### 1. Normal clone
```shell
git clone --recursive git@github.com:danielcardeenas/quandl-cpp.git
```

###### 1.1 (Optional) If you project is under git, __instead of cloning__ I recommend submoduling instead to keep up with newer versions
```shell
git submodule add git@github.com:danielcardeenas/quandl-cpp.git
git submodule update --init --recursive
```

##### 2. Next, add this subdirectory to your CMakeLists.txt before declaring any targets that might use it:

```cmake
# Compiles library 
add_subdirectory(quandl-cpp)
```

This will create the following CMake variables which you can use in any part of your project
+ `QUANDLCPP_INCLUDE_DIR` <sub>(quandlcpp .h files)</sub>
+ `JSON_INCLUDE_DIRS` <sub>(json .h files)</sub>
+ `CPR_INCLUDE_DIRS` <sub>(cpr .h files)</sub>
+ `CPR_LIBRARIES` <sub>(cpr library)</sub>
+ `QUANDLCPP_LIB` <sub>(quandlcpp library)</sub>

##### 3. Add them to your project like you normally do:
```cmake
# Include directories
include_directories(${QUANDLCPP_INCLUDE_DIR} ${CPR_INCLUDE_DIRS} ${JSON_INCLUDE_DIRS})

add_executable(...)

target_link_libraries(example quandlcpp ${QUANDLCPP_LIB} ${CPR_LIBRARIES})
```
