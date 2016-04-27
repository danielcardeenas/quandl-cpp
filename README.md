# Quandl-cpp
C++ API for Quandl

Usage:
```cpp
    quandl q;
    q.auth("qsoHq8dWs24kyT8pEDSy");
    auto json = q.request("WIKI/FB");
```

Depends on
+ cpr  https://github.com/whoshuu/cpr
+ json https://github.com/nlohmann/json
