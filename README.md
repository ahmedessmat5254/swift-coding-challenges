# swift-coding-challenges
swift coding challenges with HackingWithSwift 

## Strings
### Challenge 1 Are the letters Unique
<p>Write a function that accepts a String as its only parameter, and returns true if the string has only unique letters, taking letter case into account</p>
<p><b>Sample input and output</b></p>
<ul>
  <li> The string "No duplicates" should return true.</li>
  <li> The STring "abcdefghijklmnopqrstuvwxyz" should return true</li>
  <li>“The string “AaBbCc” should return true</li>
</ul>

### solution 

```swift
func challenge1a(input: String) -> Bool {
   var usedLetters = [Character]()
   for letter in input {
      if usedLetters.contains(letter) {
         return false
      }
      usedLetters.append(letter)
   }
return true }
  
