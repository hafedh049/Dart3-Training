The `Rune` class in Dart is used to represent Unicode code points, and it’s primarily utilized in conjunction with string manipulation. Here’s an overview of the methods available in the `Rune` class, along with examples:

### Core Dart `Rune` Methods

1. **Creating Runes**

   ```dart
   // Create a Rune from a Unicode code point
   Rune r = Rune(0x1F600); // Represents the 😀 emoji
   ```

2. **Converting to String**

   ```dart
   // Convert a Rune to a string
   Rune r = Rune(0x1F600);
   String str = String.fromCharCode(r); // '😀'
   ```

3. **Comparing Runes**

   ```dart
   Rune r1 = Rune(0x1F600); // 😀
   Rune r2 = Rune(0x1F601); // 😁

   // Compare two Runes
   bool isEqual = r1 == r2; // false
   ```

4. **Getting Unicode Code Point**

   ```dart
   Rune r = Rune(0x1F600);
   int codePoint = r; // 128512
   ```

5. **Converting Runes to List of Strings**

   ```dart
   // Convert a list of Runes to a list of strings
   List<Rune> runes = [Rune(0x1F600), Rune(0x1F601)];
   List<String> strings = runes.map((r) => String.fromCharCode(r)).toList(); // ['😀', '😁']
   ```

### Example Code

Here are some examples that demonstrate the usage of `Rune`:

```dart
void main() {
  // Creating a Rune
  Rune smiley = Rune(0x1F600); // 😀
  
  // Converting a Rune to a String
  String smileyStr = String.fromCharCode(smiley); // '😀'
  print(smileyStr); // Output: 😀

  // Comparing Runes
  Rune anotherSmiley = Rune(0x1F600);
  bool areEqual = smiley == anotherSmiley; // true
  print(areEqual); // Output: true

  // Getting the Unicode code point
  int codePoint = smiley; // 128512
  print(codePoint); // Output: 128512

  // Converting Runes to a List of Strings
  List<Rune> runes = [Rune(0x1F600), Rune(0x1F601)]; // 😀 😁
  List<String> strings = runes.map((r) => String.fromCharCode(r)).toList();
  print(strings); // Output: [😀, 😁]
}
```

### Additional Notes

- `Rune` is a simple representation and manipulation of Unicode code points. For more complex string operations involving Unicode, you might need to use additional string methods or packages.
- In practice, you often work with Runes when handling text that includes emoji or other non-ASCII characters, ensuring proper encoding and decoding in your application.