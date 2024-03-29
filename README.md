# RUTlib-py

<p align="center">
  <img src="https://github.com/RUTlib/rutlib-py/blob/main/images/rutpylib_logo.png?raw=true" alt="RUTlib's python library logo"/>
</p>

[![PyPI version](https://img.shields.io/pypi/v/RUTlib?logo=python&style=for-the-badge)](https://pypi.org/project/RUTlib/)
[![GitHub license](https://img.shields.io/github/license/RUTlib/rutlib-py?logo=python&style=for-the-badge)](https://github.com/RUTlib/rutlib-py/blob/main/LICENSE.md)

<!--
[![GitHub issues](https://img.shields.io/github/issues/RUTlib/rutlib-py?logo=python&style=for-the-badge)](https://github.com/RUTlib/rutlib-py/issues) [![GitHub forks](https://img.shields.io/github/forks/RUTlib/rutlib-py?logo=python&style=for-the-badge)](https://github.com/RUTlib/rutlib-py/network) [![GitHub stars](https://img.shields.io/github/stars/RUTlib/rutlib-py?logo=python&style=for-the-badge)](https://github.com/RUTlib/rutlib-py/stargazers)
 -->

A Python library for parsing, validating, manipulating, generating, and formatting RUTs (Chilean identification).

## Quick Installation

```bash
pip install RUTlib
```

The module exports the following functions:

- **clean_rut(rut: str) -> str**
- **validate_rut(rut: str) -> bool**
- **get_last_digit_of_rut(rut_numbers: int) -> str**
- **format_rut(rut: str, with_dots: bool = True) -> str**
- **generate_rut(length: int = 8, formatted: bool = True) -> str**

## Usage

#### Clean a RUT

This function takes a RUT as a string and removes all non-numeric characters, and transforms the input to uppercase.

```python
from RUTlib import clean_rut

print(clean_rut('1.234-3'))  # 12343
print(clean_rut('1234-3'))   # 12343
print(clean_rut('12343'))    # 12343
```

#### Validate a RUT

This function checks whether a RUT is valid according to the RUT verification rules.

```python
from RUTlib import validate_rut

print(validate_rut('1.234-3'))  # True
print(validate_rut('1234-3'))   # True
print(validate_rut('12343'))    # True
print(validate_rut('1.234-0'))  # False
```

#### Get Verificator Digit of a number

This function calculates the verification digit of a RUT.

```python
from RUTlib import get_last_digit_of_rut

print(get_last_digit_of_rut(1234))  # 3
print(get_last_digit_of_rut(1235))  # 1
```

#### Format RUT

This function formats a RUT according to RUT conventions.

```python
from RUTlib import format_rut

print(format_rut('12343'))       # 1.234-3
print(format_rut('12343', False)) # 1234-3
```

#### Generate a random RUT

This function generates a valid RUT randomly.

```python
from RUTlib import generate_rut

print(generate_rut())          # Example: 12.345.678-5 (random)
print(generate_rut(7, False))  # Example: 1234567-5 (random)
```

## Support the Project

[!["Buy Me A Coffee"](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)](https://www.buymeacoffee.com/fvergaracl)

## If you'd like to contribute

If you want to contribute to this module, please create Issues in the repository or submit Pull Requests. Remember to follow the code of conduct and best practices for clean code.

Any changes in the logic of the module's functions should be properly tested and documented.

## More information

For more information about the RUT, consult the following link: [RUT (Chile)](https://en.wikipedia.org/wiki/National_identification_number#Chile)

---

Version 0.1.3
