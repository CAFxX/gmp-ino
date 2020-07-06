# gmp-ino

GNU Multiple Precision (GMP) Arithmetic Library for Arduino.

Port of the mini-gmp library with support for arbitrary-precision integers and rational numbers. No support for floats.

Currently based on GMP v6.2.0.

Compared to vanilla mini-gmp, this library has the following modifications:

1. In case of error, no error is printed to stderr before aborting
2. The internal limb type defaults to `unsigned int` (16 bit) instead of `unsigned long` (32 bit), since AVR microcontrollers do not natively support 32-bit multiplication.

## Installing

This library is slated for inclusion in the Arduino library manager. Once included, you will be able to simply add it to your project by going in the library manager and searching for "gmp-ino".

## Usage

Sample usage:

```c
#include <gmp-ino.h>

mpz_t counter;

void setup() {
  mpz_init(counter);
}

void loop() {
  mpz_add_ui(counter, counter, 1);
}
```

## References

- [GMP website](https://gmplib.org/)
- [GMP documentation](https://gmplib.org/manual/) - note that mini-gmp supports only a subset of the full GMP library
- [mini-gmp](https://gmplib.org/repo/gmp-6.2/file/tip/mini-gmp)

## License

2020 Carlo Alberto Ferraris.

gmp-ino is licensed under the GNU LGPL v3.

GMP is dual licensed under the GNU GPL v2 or the GNU LGPL v3.
