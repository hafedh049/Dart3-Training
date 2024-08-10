Certainly! Here’s an overview of the `Map` class in Dart with examples for each method:

### Core Dart `Map` Methods

1. **Adding and Removing Key-Value Pairs**

   ```dart
   Map<String, int> scores = {'Alice': 90, 'Bob': 80};

   // Add a new key-value pair
   scores['Charlie'] = 70; // {'Alice': 90, 'Bob': 80, 'Charlie': 70}

   // Add multiple key-value pairs
   scores.addAll({'Dave': 85, 'Eve': 95}); // {'Alice': 90, 'Bob': 80, 'Charlie': 70, 'Dave': 85, 'Eve': 95}

   // Remove a key-value pair by key
   scores.remove('Charlie'); // {'Alice': 90, 'Bob': 80, 'Dave': 85, 'Eve': 95}

   // Remove all key-value pairs that match a condition
   scores.removeWhere((key, value) => value < 85); // {'Alice': 90, 'Dave': 85, 'Eve': 95}

   // Clear all key-value pairs
   scores.clear(); // {}
   ```

2. **Accessing Elements**

   ```dart
   Map<String, int> scores = {'Alice': 90, 'Bob': 80};

   // Access a value by key
   int aliceScore = scores['Alice']; // 90

   // Access a value with a default value if the key is not found
   int charlieScore = scores.putIfAbsent('Charlie', () => 75); // 75, {'Alice': 90, 'Bob': 80, 'Charlie': 75}
   ```

3. **Querying Map**

   ```dart
   Map<String, int> scores = {'Alice': 90, 'Bob': 80, 'Charlie': 75};

   // Check if the map contains a key
   bool hasAlice = scores.containsKey('Alice'); // true

   // Check if the map contains a value
   bool hasScore75 = scores.containsValue(75); // true

   // Get the number of key-value pairs
   int length = scores.length; // 3
   ```

4. **Iteration and Traversal**

   ```dart
   Map<String, int> scores = {'Alice': 90, 'Bob': 80};

   // Iterate over keys
   scores.forEach((key, value) => print('$key: $value')); 
   // prints:
   // Alice: 90
   // Bob: 80

   // Get a list of keys
   Iterable<String> keys = scores.keys; // ('Alice', 'Bob')

   // Get a list of values
   Iterable<int> values = scores.values; // (90, 80)
   ```

5. **Transformations and Projections**

   ```dart
   Map<String, int> scores = {'Alice': 90, 'Bob': 80};

   // Map each value to a new value
   Map<String, int> updatedScores = scores.map((key, value) => MapEntry(key, value + 5)); // {'Alice': 95, 'Bob': 85}

   // Transform the map into a different structure
   Iterable<String> keyValueStrings = scores.entries.map((entry) => '${entry.key}: ${entry.value}'); 
   // ('Alice: 90', 'Bob: 80')
   ```

6. **Slicing and Submaps**

   ```dart
   // Unlike lists, maps do not support direct slicing or submaps.
   // However, you can create a submap based on a condition or by copying parts of the original map.

   Map<String, int> scores = {'Alice': 90, 'Bob': 80, 'Charlie': 75};

   // Create a submap based on a condition
   Map<String, int> highScores = Map.fromEntries(scores.entries.where((entry) => entry.value >= 85)); 
   // {'Alice': 90}
   ```

7. **Other Useful Methods**

   ```dart
   Map<String, int> scores = {'Alice': 90, 'Bob': 80};

   // Convert the map to a list of key-value pairs
   List<MapEntry<String, int>> entries = scores.entries.toList(); 
   // [MapEntry('Alice', 90), MapEntry('Bob', 80)]

   // String representation of the map
   String mapString = scores.toString(); // {Alice: 90, Bob: 80}
   ```

### Methods from Other Libraries

1. **Using the `collection` package**

   ```dart
   import 'package:collection/collection.dart';

   Map<String, int> scores = {'Alice': 90, 'Bob': 80, 'Charlie': 75};

   // Group map values by a condition (converts to a list first)
   var grouped = groupBy(scores.entries.toList(), (entry) => entry.value >= 85 ? 'High' : 'Low');
   // {'High': [MapEntry('Alice', 90)], 'Low': [MapEntry('Bob', 80), MapEntry('Charlie', 75)]}
   ```

2. **Using the `quiver` package**

   ```dart
   import 'package:quiver/iterables.dart';

   Map<String, int> scores = {'Alice': 90, 'Bob': 80, 'Charlie': 75};

   // Partition the map entries into chunks of size 2 (converts to a list first)
   Iterable<List<MapEntry<String, int>>> chunks = partition(scores.entries.toList(), 2);
   // [[MapEntry('Alice', 90), MapEntry('Bob', 80)], [MapEntry('Charlie', 75)]]
   ```

These examples illustrate how to use various `Map` methods in Dart, including additional functionality provided by third-party libraries.