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
<p><b>Sample input and output</b></p>
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
-----
### Challenge 3: Do two strings contain the same characters?
Write a function that accepts two String parameters, and returns true if they contain the same characters in any order taking into account letter case.
<p><b>Sample input and output</b></p>
<ul>
  <li> The strings “abca” and “abca” should return true</li>
  <li> The strings “abc” and “cba” should return true</li>
  <li>The strings “ a1 b2 ” and “b1 a2” should return true</li>
  <li>The strings “abc” and “abca” should return false</li>
  <li>The strings “abc” and “Abc” should return false</li>
  <li> The strings “abc” and “cbAa” should return false</li>
</ul>

#### solution 1 

```swift
func challenge3a(string1: String, string2: String) -> Bool {
     
    var checkString = string2
    
    for letter in string1 {
        if let index = checkString.firstIndex(of: letter) {
            checkString.remove(at: index)
        }else {
            return false
        }
    }
    return checkString.count == 0
}
```
#### solution 2 
```swift
func challenge3b(string1: String, string2: String) -> Bool {
    let array1 = Array(string1)
    let array2 = Array(string2)
    
    return array1.count == array2.count && array1.sorted() == array2.sorted()
}
```
------
### Challenge 4: Does one string contain another?
Write your own version of the contains() method on String that ignores letter case, and
without using the existing contains() method.

#### Sample input and output
<ul>
  <li> The code "Hello, world".fuzzyContains("Hello") should return true</li>
  <li>The code "Hello, world".fuzzyContains("WORLD") should return true</li>
  <li>The code "Hello, world".fuzzyContains("Goodbye") should return false. </li>
</ul>
 
 #### solution 

```swift
extension String {
    func fuzzyContain(_ string: String) -> Bool{

        return range(of: string, options: .caseInsensitive) != nil
    }
}
```

### Challenge 5: Does one string contain another?
Write a function that accepts a string, and returns how many times a specific character appears,
taking case into account.
<b>Tip:</b> If you can solve this without using a for-in loop, you can consider it a Tricky challenge.


#### Sample input and output
<ul>
  <li> The letter “a” appears twice in “The rain in Spain”.</li>
  <li>The letter “i” appears four times in “Mississippi”.</li>
  <li>The letter “i” appears three times in “Hacking with Swift”.</li>
</ul>
 
 #### solution 1 

```swift
func challenge5a(input: String, count: Character) -> Int {
   var letterCount = 0
   for letter in input {
      if letter == count {
         letterCount += 1
      }
}
   return letterCount
}
```
 #### solution 2

```swift
func challenge5b(input: String, count: Character) -> Int {
   return input.reduce(0) {
      $1 == count ? $0 + 1 : $0
   }
}
```

 #### solution 3

```swift
func challenge5c(input: String, count: String) -> Int {
   let array = input.map { String($0) }
   let counted = NSCountedSet(array: array)
   return counted.count(for: count)
}
```



