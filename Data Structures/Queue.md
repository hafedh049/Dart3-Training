In Dart, there isn't a built-in `Queue` class in the core library, but you can use the `Queue` class from the `dart:collection` library. The `Queue` class provides a double-ended queue implementation, allowing you to efficiently add and remove elements from both ends.

Here’s an overview of the `Queue` class methods with examples:

### Core Dart `Queue` Methods

1. **Adding and Removing Elements**

   ```dart
   import 'dart:collection';

   Queue<int> queue = Queue<int>();

   // Add an element to the end
   queue.add(1); // Queue: [1]

   // Add an element to the front
   queue.addFirst(0); // Queue: [0, 1]

   // Add all elements from another iterable to the end
   queue.addAll([2, 3]); // Queue: [0, 1, 2, 3]

   // Add all elements from another iterable to the front
   queue.addFirstAll([-1, -2]); // Queue: [-2, -1, 0, 1, 2, 3]

   // Remove the first element
   int first = queue.removeFirst(); // -2, Queue: [-1, 0, 1, 2, 3]

   // Remove the last element
   int last = queue.removeLast(); // 3, Queue: [-1, 0, 1, 2]
   ```

2. **Accessing Elements**

   ```dart
   import 'dart:collection';

   Queue<int> queue = Queue<int>.from([10, 20, 30]);

   // Access the first element
   int first = queue.first; // 10

   // Access the last element
   int last = queue.last; // 30
   ```

3. **Querying Queue**

   ```dart
   import 'dart:collection';

   Queue<int> queue = Queue<int>.from([10, 20, 30]);

   // Check if the queue is empty
   bool isEmpty = queue.isEmpty; // false

   // Check if the queue is not empty
   bool isNotEmpty = queue.isNotEmpty; // true

   // Get the length of the queue
   int length = queue.length; // 3
   ```

4. **Iteration and Traversal**

   ```dart
   import 'dart:collection';

   Queue<int> queue = Queue<int>.from([10, 20, 30]);

   // Iterate over elements
   queue.forEach((element) => print(element)); 
   // prints:
   // 10
   // 20
   // 30

   // Convert the queue to a list
   List<int> list = queue.toList(); // [10, 20, 30]
   ```

5. **Transformations and Projections**

   ```dart
   import 'dart:collection';

   Queue<int> queue = Queue<int>.from([10, 20, 30]);

   // Map each element to a new value
   Queue<int> doubled = Queue<int>.from(queue.map((e) => e * 2)); // [20, 40, 60]

   // Filter elements based on a condition
   Queue<int> filtered = Queue<int>.from(queue.where((e) => e > 15)); // [20, 30]
   ```

6. **Other Useful Methods**

   ```dart
   import 'dart:collection';

   Queue<int> queue = Queue<int>.from([10, 20, 30]);

   // Convert the queue to a string representation
   String queueString = queue.toString(); // [10, 20, 30]
   ```

### Methods from Other Libraries

Additional functionality or specialized queue implementations might come from third-party libraries. Some common libraries for advanced data structures include:

1. **Using the `collection` package**

   ```dart
   import 'package:collection/collection.dart';

   Queue<int> queue = Queue<int>.from([10, 20, 30]);

   // No specific additional queue methods, but you can use general collection utilities
   ```

2. **Using the `quiver` package**

   ```dart
   import 'package:quiver/collections.dart';

   // The quiver package provides a `PriorityQueue`, which is different from a regular queue
   PriorityQueue<int> pq = PriorityQueue<int>((a, b) => a.compareTo(b));
   pq.addAll([3, 1, 2]);

   // Access the highest priority element
   int highest = pq.removeFirst(); // 1
   ```

The examples above cover the most commonly used methods for the `Queue` class in Dart, including some advanced functionalities from popular packages.