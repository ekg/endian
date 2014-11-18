# Endian
## C++ header library for endianness detection and manipulation
### *pulled from lovely comments on stackoverflow*

Header-only library (endian.h) to handle conversion between big and
little-endian format. It includes a runtime check of system endianness.

Use as such to force to big-endian:

    int64_t j = to_big_endian<int64_t>(i);

Or, to force to little-endian:

    int64_t j = to_little_endian<int64_t>(i);

Or first detect if you need to swap endianness at all:

    bool should_swap = IsBigEndian();
    /* ... */
    if (should_swap) {
        i = swap_endian<int64_t>(i);
    }

Author: Erik Garrison

License: MIT
