# Endian

> *pulled from lovely comments on stackoverflow*
> All references to original source are in endian.hpp

Header-only library (endian.hpp) to handle conversion between big and
little-endian format.

### Usage

You can just copy the endian.hpp file to your project,
or if using with CPM.cmake, add this in CMakeLists.txt:
```
CPMAddPackage("gh:adi-g15/endian@1.0")
```

#### Converting to big-endian:
```cpp
    int64_t j = endian::to_big_endian<int64_t>(i);
```

#### Converting to little-endian:
```cpp
    int64_t j = endian::to_little_endian<int64_t>(i);
```

#### Checking endianness

> Note regarding C++20: C++20 provides 
[std::endian](https://en.cppreference.com/w/cpp/types/endian) to check endian
> at compile time
> Just to remain C++11, this includes a runtime check of system endianness.

```cpp
    bool is_big_endian = endian::IsBigEndian();
```

#### Swapping endianness
Maybe first check if you need to swap endianness at all:
```cpp
    bool should_swap = IsBigEndian();
    /* ... */
    if (should_swap) {
        i = endian::swap_endian<int64_t>(i);
    }
```

Author: Erik Garrison

License: MIT
