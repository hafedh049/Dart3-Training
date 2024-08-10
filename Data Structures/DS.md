Dart 3.12.3, like earlier versions, provides a range of built-in data structures that are essential for managing collections of data. Here's a list of the primary data structures available in Dart:

### 1. **List**
   - **Description**: An ordered collection of objects, also known as an array. Lists can grow or shrink in size.
   - **Types**: 
     - Fixed-length List
     - Growable List

### 2. **Set**
   - **Description**: An unordered collection of unique objects. Sets do not allow duplicate elements.
   - **Types**:
     - HashSet (default)
     - LinkedHashSet (maintains insertion order)
     - SplayTreeSet (sorted order)

### 3. **Map**
   - **Description**: A collection of key-value pairs, where each key is unique. Maps allow fast retrieval, updating, and removal of key-value pairs.
   - **Types**:
     - HashMap (default)
     - LinkedHashMap (maintains insertion order)
     - SplayTreeMap (sorted order)

### 4. **Queue**
   - **Description**: A collection that supports insertion at the end and removal from the beginning (FIFO - First In, First Out).
   - **Types**:
     - Double-linked List (Deque)

### 5. **Iterable**
   - **Description**: An abstract class for collections that can be iterated over. Lists, Sets, and Maps are all subtypes of Iterable.

### 6. **Runes**
   - **Description**: A special data structure that represents Unicode code points in a string. This is useful for working with extended Unicode characters.

### 7. **String**
   - **Description**: Although not a traditional data structure, Dart treats `String` as a sequence of UTF-16 code units, making it iterable.

### 8. **Record (introduced in Dart 3)**
   - **Description**: A lightweight data structure that groups a fixed number of items together. Records can hold multiple fields of various types and can be compared for equality based on their contents.

### 9. **Future**
   - **Description**: A data structure representing a potential value or error that will be available at some time in the future. Often used for asynchronous programming.

### 10. **Stream**
   - **Description**: A data structure that provides a sequence of asynchronous data events. Useful for handling multiple asynchronous events in a Dart application.

These data structures offer a robust foundation for building complex applications in Dart 3.12.3, making it easier to manage and manipulate collections of data.