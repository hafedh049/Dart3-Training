In Dart, a `Stream` is used for handling asynchronous sequences of data. It represents a series of events or data over time. Here’s an overview of the methods available in the `Stream` class, with examples:

### Core Dart `Stream` Methods

1. **Creating Streams**

   ```dart
   // Create a stream from a list
   Stream<int> streamFromList = Stream.fromIterable([1, 2, 3]);

   // Create a stream that emits a value after a delay
   Stream<int> delayedStream = Stream<int>.periodic(Duration(seconds: 1), (count) => count).take(3);
   ```

2. **Listening to Streams**

   ```dart
   // Listen to a stream
   streamFromList.listen((value) {
     print(value); // Output: 1, 2, 3
   });

   // Listen to a stream with onError and onDone handlers
   delayedStream.listen(
     (value) => print('Value: $value'),  // Handle data
     onError: (error) => print('Error: $error'), // Handle errors
     onDone: () => print('Stream done'), // Handle stream completion
   );
   ```

3. **Transforming Streams**

   ```dart
   // Transform stream data using map
   Stream<String> transformedStream = streamFromList.map((value) => 'Number: $value');
   transformedStream.listen((value) => print(value)); // Output: Number: 1, Number: 2, Number: 3

   // Filter stream data using where
   Stream<int> filteredStream = streamFromList.where((value) => value.isEven);
   filteredStream.listen((value) => print(value)); // Output: 2
   ```

4. **Combining Streams**

   ```dart
   // Combine multiple streams using merge
   Stream<int> stream1 = Stream.fromIterable([1, 2]);
   Stream<int> stream2 = Stream.fromIterable([3, 4]);

   Stream<int> mergedStream = StreamGroup.merge([stream1, stream2]);
   mergedStream.listen((value) => print(value)); // Output: 1, 2, 3, 4
   ```

5. **Buffering Streams**

   ```dart
   // Buffer stream data using buffer
   Stream<List<int>> bufferedStream = streamFromList.transform(StreamTransformer.fromHandlers(
     handleData: (data, sink) {
       // Collect data into a list
       List<int> buffer = [];
       buffer.add(data);
       sink.add(buffer);
     },
   ));

   bufferedStream.listen((buffer) => print(buffer)); // Output: [1], [2], [3]
   ```

6. **Handling Errors**

   ```dart
   // Create a stream with an error
   Stream<int> errorStream = Stream.error('An error occurred');

   // Handle errors with onError
   errorStream.listen(
     (value) => print(value),
     onError: (error) => print('Error: $error'), // Output: Error: An error occurred
   );
   ```

7. **Closing Streams**

   ```dart
   // Create a broadcast stream and close it
   StreamController<int> controller = StreamController<int>();
   Stream<int> broadcastStream = controller.stream.asBroadcastStream();

   broadcastStream.listen((value) => print(value));
   controller.add(1);
   controller.add(2);
   controller.close();
   ```

8. **Converting Streams to Future**

   ```dart
   // Convert a single-value stream to a future
   Future<int> futureValue = Stream.fromIterable([1]).single;
   futureValue.then((value) => print(value)); // Output: 1

   // Convert a stream to a list
   Future<List<int>> futureList = streamFromList.toList();
   futureList.then((list) => print(list)); // Output: [1, 2, 3]
   ```

9. **Waiting for Streams**

   ```dart
   // Wait for a stream to complete
   Future<void> waitForStream = delayedStream.drain();
   waitForStream.then(() => print('Stream drained')); // Output: Stream drained
   ```

### Example Code

Here are some practical examples demonstrating various `Stream` methods:

```dart
import 'dart:async';

void main() {
  // Create a stream from a list
  Stream<int> streamFromList = Stream.fromIterable([1, 2, 3]);

  // Listen to the stream
  streamFromList.listen((value) {
    print('Received: $value'); // Output: Received: 1, Received: 2, Received: 3
  });

  // Transform and filter streams
  Stream<String> transformedStream = streamFromList.map((value) => 'Number: $value');
  Stream<int> filteredStream = streamFromList.where((value) => value.isEven);

  transformedStream.listen((value) => print('Transformed: $value')); // Output: Transformed: Number: 1, Transformed: Number: 2, Transformed: Number: 3
  filteredStream.listen((value) => print('Filtered: $value')); // Output: Filtered: 2

  // Combine multiple streams
  Stream<int> stream1 = Stream.fromIterable([1, 2]);
  Stream<int> stream2 = Stream.fromIterable([3, 4]);

  Stream<int> mergedStream = StreamGroup.merge([stream1, stream2]);
  mergedStream.listen((value) => print('Merged: $value')); // Output: Merged: 1, Merged: 2, Merged: 3, Merged: 4

  // Buffer and handle errors
  Stream<int> errorStream = Stream.error('An error occurred');
  errorStream.listen(
    (value) => print(value),
    onError: (error) => print('Error: $error'), // Output: Error: An error occurred
  );

  // Convert stream to future and list
  Future<int> futureValue = Stream.fromIterable([1]).single;
  futureValue.then((value) => print('Future value: $value')); // Output: Future value: 1

  Future<List<int>> futureList = streamFromList.toList();
  futureList.then((list) => print('List: $list')); // Output: List: [1, 2, 3]
}
```

### Additional Notes

- **Broadcast Streams**: Streams can be broadcast, allowing multiple listeners to receive data. This is useful when you need to share a single stream with multiple subscribers.
- **Stream Transformers**: Custom stream transformers can be used to modify stream data, buffer data, or handle other stream processing tasks.

Streams provide a powerful way to handle asynchronous sequences and events, making them an essential part of Dart's asynchronous programming model.