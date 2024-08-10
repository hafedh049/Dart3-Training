In Dart, the `Future` class represents a computation that might not have completed yet but will eventually provide a result or error. Here’s an overview of the methods available in the `Future` class, along with examples:

### Core Dart `Future` Methods

1. **Creating Futures**

   ```dart
   // Create a future that completes with a value
   Future<int> futureValue = Future.value(42);

   // Create a future that completes with an error
   Future<int> futureError = Future.error('An error occurred');
   ```

2. **Awaiting a Future**

   ```dart
   Future<int> futureValue = Future.value(42);

   // Await the result of the future
   void example() async {
     int value = await futureValue;
     print(value); // Output: 42
   }
   ```

3. **Handling Results**

   ```dart
   Future<int> futureValue = Future.value(42);

   // Handle result with then
   futureValue.then((value) {
     print(value); // Output: 42
   });

   // Handle error with catchError
   Future<int> futureError = Future.error('An error occurred');
   futureError.catchError((error) {
     print(error); // Output: An error occurred
   });
   ```

4. **Chaining Futures**

   ```dart
   Future<int> futureValue = Future.value(42);

   // Chain multiple futures
   futureValue
     .then((value) => value + 1)
     .then((newValue) => print(newValue)); // Output: 43
   ```

5. **Combining Futures**

   ```dart
   Future<int> future1 = Future.value(1);
   Future<int> future2 = Future.value(2);

   // Combine multiple futures with Future.wait
   Future<List<int>> combinedFuture = Future.wait([future1, future2]);
   combinedFuture.then((values) {
     print(values); // Output: [1, 2]
   });
   ```

6. **Completing a Future**

   ```dart
   // Create a completer
   Completer<int> completer = Completer<int>();

   // Complete the future with a value
   completer.complete(42);
   completer.future.then((value) => print(value)); // Output: 42

   // Complete the future with an error
   Completer<int> errorCompleter = Completer<int>();
   errorCompleter.completeError('An error occurred');
   errorCompleter.future.catchError((error) => print(error)); // Output: An error occurred
   ```

7. **Other Useful Methods**

   ```dart
   // Create a future that completes after a delay
   Future<void> delayedFuture = Future.delayed(Duration(seconds: 1), () => print('Delayed Future'));

   // Wait for a future to complete
   Future<int> futureValue = Future.value(42);
   futureValue.whenComplete(() => print('Future completed')); // Output: Future completed
   ```

### Example Code

Here are some examples demonstrating various `Future` methods:

```dart
import 'dart:async';

void main() async {
  // Create a Future with a value
  Future<int> futureValue = Future.value(42);

  // Await the result
  int value = await futureValue;
  print(value); // Output: 42

  // Handle result with then
  futureValue.then((value) => print('Value: $value')); // Output: Value: 42

  // Handle error with catchError
  Future<int> futureError = Future.error('An error occurred');
  futureError.catchError((error) => print('Error: $error')); // Output: Error: An error occurred

  // Chain multiple futures
  futureValue
    .then((value) => value + 1)
    .then((newValue) => print('Chained Value: $newValue')); // Output: Chained Value: 43

  // Combine multiple futures with Future.wait
  Future<int> future1 = Future.value(1);
  Future<int> future2 = Future.value(2);
  Future<List<int>> combinedFuture = Future.wait([future1, future2]);
  combinedFuture.then((values) => print('Combined Future: $values')); // Output: Combined Future: [1, 2]

  // Create and complete a Completer
  Completer<int> completer = Completer<int>();
  completer.complete(42);
  completer.future.then((value) => print('Completer Value: $value')); // Output: Completer Value: 42

  // Create a Future that completes after a delay
  Future<void> delayedFuture = Future.delayed(Duration(seconds: 1), () => print('Delayed Future'));

  // Wait for a future to complete
  await delayedFuture;
  print('Done waiting for delayed future');
}
```

### Additional Notes

- **`Future` vs. `Completer`**: `Future` is used for handling asynchronous operations, while `Completer` is used to manually complete a future with a value or an error.
- **Error Handling**: `catchError` and `whenComplete` methods are useful for handling errors and performing actions after the future completes, regardless of whether it completes with a value or an error.