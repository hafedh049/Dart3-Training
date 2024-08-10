Sure! Here are the `List` methods in Dart with examples for each:

### Core Dart `List` Methods

1. **Adding and Removing Elements**

   ```dart
   List<int> numbers = [1, 2, 3];

   // Add a single element
   numbers.add(4); // [1, 2, 3, 4]

   // Add all elements from another iterable
   numbers.addAll([5, 6]); // [1, 2, 3, 4, 5, 6]

   // Insert an element at a specific index
   numbers.insert(2, 10); // [1, 2, 10, 3, 4, 5, 6]

   // Insert all elements from an iterable at a specific index
   numbers.insertAll(4, [20, 30]); // [1, 2, 10, 3, 20, 30, 4, 5, 6]

   // Remove the first occurrence of a value
   numbers.remove(10); // [1, 2, 3, 20, 30, 4, 5, 6]

   // Remove element at a specific index
   numbers.removeAt(4); // [1, 2, 3, 20, 4, 5, 6]

   // Remove the last element
   numbers.removeLast(); // [1, 2, 3, 20, 4, 5]

   // Remove a range of elements
   numbers.removeRange(1, 4); // [1, 4, 5]

   // Clear all elements
   numbers.clear(); // []
   ```

2. **Accessing Elements**

   ```dart
   List<String> fruits = ['apple', 'banana', 'cherry'];

   // Access element by index
   String fruit = fruits[1]; // 'banana'

   // Modify element by index
   fruits[1] = 'blueberry'; // ['apple', 'blueberry', 'cherry']
   ```

3. **Querying List**

   ```dart
   List<String> animals = ['dog', 'cat', 'dog', 'fish'];

   // Length of the list
   int length = animals.length; // 4

   // Check if the list is empty
   bool isEmpty = animals.isEmpty; // false

   // Check if the list is not empty
   bool isNotEmpty = animals.isNotEmpty; // true

   // Check if the list contains a value
   bool containsDog = animals.contains('dog'); // true

   // Index of the first occurrence of a value
   int index = animals.indexOf('dog'); // 0

   // Index of the last occurrence of a value
   int lastIndex = animals.lastIndexOf('dog'); // 2
   ```

4. **Sorting and Reordering**

   ```dart
   List<int> numbers = [5, 2, 8, 1];

   // Sort the list in ascending order
   numbers.sort(); // [1, 2, 5, 8]

   // Reverse the list
   Iterable<int> reversed = numbers.reversed; // [8, 5, 2, 1]
   ```

5. **Transformations and Projections**

   ```dart
   List<int> numbers = [1, 2, 3];

   // Map each element to a new value
   Iterable<int> squared = numbers.map((e) => e * e); // [1, 4, 9]

   // Filter elements based on a condition
   Iterable<int> evens = numbers.where((e) => e.isEven); // [2]

   // Expand elements into multiple values
   Iterable<int> expanded = numbers.expand((e) => [e, e * 2]); // [1, 2, 2, 4, 3, 6]
   ```

6. **Slicing and Sublists**

   ```dart
   List<int> numbers = [1, 2, 3, 4, 5];

   // Create a sublist
   List<int> sublist = numbers.sublist(1, 4); // [2, 3, 4]
   ```

7. **List Operations**

   ```dart
   List<int> numbers = [1, 2, 3];

   // Apply a function to each element
   numbers.forEach((e) => print(e)); // prints: 1 2 3

   // Combine all elements into a single value
   int sum = numbers.fold(0, (prev, e) => prev + e); // 6

   // Reduce the list to a single value
   int product = numbers.reduce((value, e) => value * e); // 6
   ```

8. **Other Useful Methods**

   ```dart
   List<int> numbers = [1, 2, 3, 2, 1];

   // Convert list to a set to remove duplicates
   Set<int> uniqueNumbers = numbers.toSet(); // {1, 2, 3}

   // String representation of the list
   String listString = numbers.toString(); // [1, 2, 3, 2, 1]
   ```

### Methods from Other Libraries

1. **Using the `collection` package**

   ```dart
   import 'package:collection/collection.dart';

   List<int> numbers = [1, 2, 3, 4, 5];

   // Group list elements by a key
   var grouped = groupBy(numbers, (int n) => n % 2); // {1: [1, 3, 5], 0: [2, 4]}
   ```

2. **Using the `quiver` package**

   ```dart
   import 'package:quiver/iterables.dart';

   List<int> numbers = [1, 2, 3, 4, 5];

   // Partition the list into chunks of size 2
   Iterable<List<int>> chunks = partition(numbers, 2); // [[1, 2], [3, 4], [5]]
   ```

These examples illustrate how to use various `List` methods in Dart, including additional functionality provided by third-party libraries.