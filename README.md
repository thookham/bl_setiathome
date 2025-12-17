# Breakthrough Listen SETI@home Requantization Tools

Requantization tools for Radio Astronomy. Currently only supports 8-bit integer to 2-bit data.

This project is built with [pybind11](https://github.com/pybind/pybind11).

## Authors

Danny Price and Sam Weissman

## Requirements

* pybind11 >= 2.2

## Installation

**On Unix (Linux, OS X)**

* Clone this repository
* `python setup.py build_ext -i` to build shared object .so locally, or
* `python setup.py install` to install globally

## Usage

```python
import numpy as np
import requant_utils

# Create input array (8-bit signed integers)
a = np.array([-3, -2, -1, 0, 1, 2, 3, 4], dtype='int8')

# Create output array (unsigned 8-bit integers, 1/4th the size)
# Note: The output is packed 2-bit data
b = np.zeros(int(a.shape[0]/4), dtype='uint8')

# Run requantization
requant_utils.requant_8i_2u(a, b)
```
