# ZKFloat
## About
ZKFLoat library adds support for representing floating point values and performing abasic arythmetic operations over floating point numbers. The numbers are represented as a base 10 floating point values in format inspired by [IEEE 754](https://standards.ieee.org/ieee/754/6210/) format for representing floating points using base 2. The structure consists of a sign, mantissa and exponent. Due to a current lack of support for signed data types in [Noir](https://noir-lang.org/) language, explicit representation of a sign value is required. Mantissa is represented using <i>p</i> number of significant digits, which equals 7 in the basic form but can be altered. As exponent value can also be negative values, current implementation uses exponent value centered around a specified positive value. In current value, the center value is 100, meaning that 0 exponent equals 100 in transformed format.

The library implements `Float` structure representing floating point values, as well as operations for addition, subtraction and multiplications of the values. Each operation keeps first <i>p</i> number of digits in mantissa and updates exponent value of the result when needed.

### Implemented methods
- `addFloats` - Addition of floats
- `mulFloats` - Multiplication of floats
- `subFloats` - Subtraction of floats
- `truncate` - Internal method for truncating mantissa values which overflows the 
maximum number of significant digits.
- `relu` - ReLU activation function, used in ANN models.

## Future work
- Support for division operation
- Removing explicit sign attribute when [Noir](https://noir-lang.org/) language adds support for signed values
- More complex arithmetic operations