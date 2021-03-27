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

#### solution 1 

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
```
#### solution 2 
```swift
func Challange1b(input: String) -> Bool {
    return Set(input).count == input.count
}
```

-----

### Challenge 2 Is a String a palindrome ?
Write a function that accepts a String as its only parameter, and returns true if the string
reads the same when reversed, ignoring case.
<ul> 
  <li>The string “rotator” should return true. </li>
  <li>The string “Rats live on no evil star” should return true. </li>
  <li>The string “Never odd or even” should return false; even though the letters are the
same in reverse the spaces are in different places. </li>
  <li> The string “Hello, world” should return false because it reads “dlrow ,olleH”
backwards.</li>
</ul>

#### solution 

```swift
func challenge2(input: String) -> Bool{
    let lowercase = input.lowercased()
    return input.reversed() == Array(lowercase)
}
```
