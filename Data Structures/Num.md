In Dart, `num` is an abstract class that serves as the superclass for both `int` and `double`. It provides methods and properties that are common to numeric types. Here's a list of all the methods available in the `num` class along with examples:

### Core Dart `num` Methods

1. **Converting to `int`**

   ```dart
   num number = 42.5;

   // Convert to int (truncates the decimal part)
   int integerPart = number.toInt();
   print(integerPart); // Output: 42
   ```

2. **Converting to `double`**

   ```dart
   num number = 42;

   // Convert to double
   double doubleValue = number.toDouble();
   print(doubleValue); // Output: 42.0
   ```

3. **Parsing Strings**

   ```dart
   // Parse a string to an int
   int parsedInt = int.parse('42');
   print(parsedInt); // Output: 42

   // Parse a string to a double
   double parsedDouble = double.parse('42.5');
   print(parsedDouble); // Output: 42.5
   ```

4. **Checking for Zero**

   ```dart
   num number = 0;

   // Check if the number is zero
   bool isZero = number == 0;
   print(isZero); // Output: true
   ```

5. **Checking for Infinity**

   ```dart
   num positiveInfinity = double.infinity;
   num negativeInfinity = double.negativeInfinity;

   // Check for positive infinity
   bool isPositiveInfinity = positiveInfinity.isInfinite && positiveInfinity.isNegative == false;
   print(isPositiveInfinity); // Output: true

   // Check for negative infinity
   bool isNegativeInfinity = negativeInfinity.isInfinite && negativeInfinity.isNegative == true;
   print(isNegativeInfinity); // Output: true
   ```

6. **Checking for NaN (Not a Number)**

   ```dart
   num notANumber = double.nan;

   // Check if the number is NaN
   bool isNan = notANumber.isNaN;
   print(isNan); // Output: true
   ```

7. **Clamping Values**

   ```dart
   num number = 15;

   // Clamp the number between a minimum and maximum value
   num clampedValue = number.clamp(10, 20);
   print(clampedValue); // Output: 15

   // Clamp a value that is below the minimum
   num belowMinClamp = number.clamp(20, 30);
   print(belowMinClamp); // Output: 20

   // Clamp a value that is above the maximum
   num aboveMaxClamp = number.clamp(5, 10);
   print(aboveMaxClamp); // Output: 10
   ```

8. **Comparing Values**

   ```dart
   num a = 5;
   num b = 10;

   // Compare two numbers
   int comparisonResult = a.compareTo(b);
   print(comparisonResult); // Output: -1 (a < b)

   // Compare with zero
   int comparisonWithZero = a.compareTo(0);
   print(comparisonWithZero); // Output: 1 (a > 0)
   ```

### Example Code

Here are practical examples demonstrating various `num` methods:

```dart
void main() {
  num number = 42.5;

  // Convert to int
  int integerPart = number.toInt();
  print('Integer part: $integerPart'); // Output: Integer part: 42

  // Convert to double
  double doubleValue = number.toDouble();
  print('Double value: $doubleValue'); // Output: Double value: 42.5

  // Parse string to int and double
  int parsedInt = int.parse('42');
  double parsedDouble = double.parse('42.5');
  print('Parsed int: $parsedInt'); // Output: Parsed int: 42
  print('Parsed double: $parsedDouble'); // Output: Parsed double: 42.5

  // Check if the number is zero
  num zeroNumber = 0;
  bool isZero = zeroNumber == 0;
  print('Is zero: $isZero'); // Output: Is zero: true

  // Check for infinity and NaN
  num posInf = double.infinity;
  num negInf = double.negativeInfinity;
  num nan = double.nan;

  bool isPositiveInfinity = posInf.isInfinite && !posInf.isNegative;
  bool isNegativeInfinity = negInf.isInfinite && negInf.isNegative;
  bool isNan = nan.isNaN;

  print('Is positive infinity: $isPositiveInfinity'); // Output: Is positive infinity: true
  print('Is negative infinity: $isNegativeInfinity'); // Output: Is negative infinity: true
  print('Is NaN: $isNan'); // Output: Is NaN: true

  // Clamping values
  num clampedValue = number.clamp(10, 20);
  num belowMinClamp = number.clamp(20, 30);
  num aboveMaxClamp = number.clamp(5, 10);

  print('Clamped value: $clampedValue'); // Output: Clamped value: 15
  print('Below min clamp: $belowMinClamp'); // Output: Below min clamp: 20
  print('Above max clamp: $aboveMaxClamp'); // Output: Above max clamp: 10

  // Comparing values
  num a = 5;
  num b = 10;

  int comparisonResult = a.compareTo(b);
  int comparisonWithZero = a.compareTo(0);

  print('Comparison result: $comparisonResult'); // Output: Comparison result: -1
  print('Comparison with zero: $comparisonWithZero'); // Output: Comparison with zero: 1
}
```

### Additional Notes

- **`num` Class**: The `num` class itself is abstract and cannot be instantiated directly. It is implemented by `int` and `double`.
- **`NaN` and Infinity**: `NaN` and infinity values are represented using `double.nan`, `double.infinity`, and `double.negativeInfinity`.

These methods and properties provide a wide range of functionality for handling numeric values in Dart, making it easier to work with different types of numbers and perform various mathematical operations.

In Dart, the `num` class provides a set of attributes and methods common to both `int` and `double`. While the `num` class itself doesn't have attributes that are directly accessible, its concrete implementations (`int` and `double`) do. Here’s a breakdown of attributes and methods available in the `num` class and its implementations:

### `num` Class

#### Attributes
- **`isNegative`**: Indicates if the number is negative. This is a property available in `double` but not directly in `num`.

### `int` Class

#### Attributes
- **`isEven`**: Returns `true` if the integer is even.
  ```dart
  int value = 4;
  bool even = value.isEven;
  print(even); // Output: true
  ```

- **`isOdd`**: Returns `true` if the integer is odd.
  ```dart
  int value = 5;
  bool odd = value.isOdd;
  print(odd); // Output: true
  ```

- **`bitLength`**: Returns the number of bits required to represent the integer in binary, excluding the sign bit.
  ```dart
  int value = 255;
  int bits = value.bitLength;
  print(bits); // Output: 8
  ```

### `double` Class

#### Attributes
- **`isNaN`**: Returns `true` if the number is NaN (Not a Number).
  ```dart
  double nanValue = double.nan;
  bool isNan = nanValue.isNaN;
  print(isNan); // Output: true
  ```

- **`isInfinite`**: Returns `true` if the number is either positive or negative infinity.
  ```dart
  double positiveInfinity = double.infinity;
  bool isPositiveInf = positiveInfinity.isInfinite;
  print(isPositiveInf); // Output: true
  ```

- **`isNegative`**: Returns `true` if the number is negative. This is a property of `double`.
  ```dart
  double negativeValue = -1.5;
  bool isNegative = negativeValue.isNegative;
  print(isNegative); // Output: true
  ```

### Example Code

Here is an example demonstrating the use of these attributes:

```dart
void main() {
  int integerValue = 42;
  double doubleValue = -3.14;

  // int attributes
  print('Integer is even: ${integerValue.isEven}'); // Output: Integer is even: true
  print('Integer is odd: ${integerValue.isOdd}'); // Output: Integer is odd: false
  print('Bit length of integer: ${integerValue.bitLength}'); // Output: Bit length of integer: 6

  // double attributes
  double nanValue = double.nan;
  double positiveInf = double.infinity;
  double negativeValue = -1.5;

  print('Double is NaN: ${nanValue.isNaN}'); // Output: Double is NaN: true
  print('Double is infinite: ${positiveInf.isInfinite}'); // Output: Double is infinite: true
  print('Double is negative: ${negativeValue.isNegative}'); // Output: Double is true
}
```

### Summary

- **`num`**: Abstract class, no direct attributes.
- **`int`**: `isEven`, `isOdd`, `bitLength`.
- **`double`**: `isNaN`, `isInfinite`, `isNegative`.

These attributes and methods allow you to perform various numeric checks and operations in Dart, enhancing the flexibility and control you have over numeric data.