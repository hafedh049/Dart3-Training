Certainly! Here are the methods available for Dart’s `Set` class with examples for each:

### Core Dart `Set` Methods

1. **Adding and Removing Elements**

   ```dart
   Set<int> numbers = {1, 2, 3};

   // Add a single element
   numbers.add(4); // {1, 2, 3, 4}

   // Add all elements from another iterable
   numbers.addAll([5, 6]); // {1, 2, 3, 4, 5, 6}

   // Remove a specific element
   numbers.remove(4); // {1, 2, 3, 5, 6}

   // Remove all elements from another iterable
   numbers.removeAll([2, 5]); // {1, 3, 6}

   // Remove elements that satisfy a condition
   numbers.removeWhere((e) => e.isOdd); // {6}

   // Clear all elements from the set
   numbers.clear(); // {}
   ```

2. **Accessing Elements**

   ```dart
   Set<String> fruits = {'apple', 'banana', 'cherry'};

   // Check if a set contains an element
   bool hasApple = fruits.contains('apple'); // true

   // Get the number of elements
   int length = fruits.length; // 3
   ```

3. **Querying Set**

   ```dart
   Set<int> numbers = {1, 2, 3, 4, 5};

   // Check if the set is empty
   bool isEmpty = numbers.isEmpty; // false

   // Check if the set is not empty
   bool isNotEmpty = numbers.isNotEmpty; // true
   ```

4. **Set Operations**

   ```dart
   Set<int> setA = {1, 2, 3};
   Set<int> setB = {3, 4, 5};

   // Union of two sets
   Set<int> union = setA.union(setB); // {1, 2, 3, 4, 5}

   // Intersection of two sets
   Set<int> intersection = setA.intersection(setB); // {3}

   // Difference between two sets
   Set<int> difference = setA.difference(setB); // {1, 2}

   // Symmetric difference between two sets (elements in either set but not both)
   Set<int> symmetricDifference = setA.union(setB).difference(setA.intersection(setB)); // {1, 2, 4, 5}
   ```

5. **Transformations and Projections**

   ```dart
   Set<int> numbers = {1, 2, 3};

   // Map each element to a new value
   Iterable<int> squared = numbers.map((e) => e * e); // (1, 4, 9)

   // Filter elements based on a condition
   Iterable<int> evens = numbers.where((e) => e.isEven); // (2)
   ```

6. **Slicing and Sublists**

   ```dart
   // Unlike lists, sets do not support slicing or sublists directly.
   // However, you can convert a set to a list to perform these operations.

   List<int> numberList = numbers.toList(); // [1, 2, 3]

   // Create a sublist from the list representation
   List<int> sublist = numberList.sublist(1, 3); // [2, 3]
   ```

7. **List Operations**

   ```dart
   Set<int> numbers = {1, 2, 3};

   // Apply a function to each element
   numbers.forEach((e) => print(e)); // prints: 1 2 3
   ```

8. **Other Useful Methods**

   ```dart
   Set<int> numbers = {1, 2, 3, 2, 1};

   // Convert the set to a list
   List<int> list = numbers.toList(); // [1, 2, 3]

   // String representation of the set
   String setString = numbers.toString(); // {1, 2, 3}
   ```

### Methods from Other Libraries

1. **Using the `collection` package**

   ```dart
   import 'package:collection/collection.dart';

   Set<int> numbers = {1, 2, 3, 4, 5};

   // Group set elements by a key (converts to a list first)
   var grouped = groupBy(numbers.toList(), (int n) => n % 2); // {1: [1, 3, 5], 0: [2, 4]}
   ```

2. **Using the `quiver` package**

   ```dart
   import 'package:quiver/iterables.dart';

   Set<int> numbers = {1, 2, 3, 4, 5};

   // Partition the set into chunks of size 2 (converts to a list first)
   Iterable<List<int>> chunks = partition(numbers.toList(), 2); // [[1, 2], [3, 4], [5]]
   ```

These examples demonstrate how to work with Dart's `Set` class, including additional functionality provided by popular libraries.