# Strings Lab 1

## Instructions for lab submission

1. Fork the assignment repo
1. Clone your Fork to your machine
1. Complete the lab
1. Push your changes to your Fork
1. Submit a Pull Request back to the assignment repo
1. Paste a link to of your Fork on Canvas and submit

## Question 1

Write code that prints out all the numbers from 1 to 10 as a single string.
(Hint: the `String()` function can convert an Int to a String)

Answer:
```swift
let range = 1...10
for number in range {
print(String(number), terminator: " ")
}
```

***
## Question 2

Write code that prints out all the even numbers from 5 to 51 as a single string.

Answer:
```swift
let range = 5...51
for number in range {
if number % 2 == 0 {
print(String(number), terminator: " ")
}
}
```

***
## Question 3

Write code that prints out every number ending in 4 between 1 and 60 as a single string.

Answer:
```swift
let range = 1...60
for number in range {
if number % 10 == 4 {
print(String(number), terminator: " ")
}
}
```

***
## Question 4

Print each character in the string `"Hello world!"`

Answer:
```swift
let string = "Hello world!"

for letter in string {
print(letter)
}
```

***
## Question 5

Print out the last character in the string below.  You cannot use the Character literal "!" (i.e you must access `myStringSeven`'s characters).

`let myStringSeven = "Hello world!"`

Answer:
```swift
let myStringSeven = "Hello world!"

print(myStringSeven.removeLast())
```

***
## Question 6

Write code that switches on a string, given the following conditions:
- If the string's length is even, print out every character.
- If the string's length is odd, print out every other character.

Answer:
```swift
let string = "Odd or even"

if string.count % 2 == 0 {
for letter in string {
print (letter, terminator: "")
}
} else {
for (index,element) in string.enumerated() {
if index % 2 != 0 {
print (element, terminator: "")
}
}
}
````


***
## Question 7

Initialize a String with a character. Show that it is a Character, and not another String, that you're using to initialize it.

Answer:
```swift
let string = "a"

print(Character(string) == Character("a"))
```

***
## Question 8*****

Build five pairs of **canonically equivalent** strings, the first of each being a pre-composed character and the second being one that uses combinable unicode scalars. Show that they are equivalent.

Answer:
```swift
//Pair 1
let a = "\u{0061}"
let umlaut = "\u{0308}"
let aUmlautPrecomposed = "\u{00E4}"
let aUmlautScalars = "\u{0061}\u{0308}"

print(aUmlautPrecomposed == aUmlautScalars)

//Pair 2
let n = "\u{006E}"
let tilde = "\u{0303}"
let nTildePrecomposed = "\u{00F1}"
let nTildeScalars = "\u{006E}\u{0303}"

print(nTildePrecomposed == nTildeScalars)

//Pair 3
let c = "\u{0063}"
let cedilla = "\u{0327}"
let cCedillaPrecomposed = "\u{00E7}"
let cCedillaScalars = "\u{0063}\u{0327}"

print(cCedillaPrecomposed == cCedillaScalars)

//Pair 4
let o = "\u{006F}"
let graveAccent = "\u{0300}"
let oGravePrecomposed = "\u{00F2}"
let oGraveScalar = "\u{006F}\u{0300}"

print(oGravePrecomposed == oGraveScalar)

//Pair 5
let hangulG = "\u{1100}"
let hangulA = "\u{1161}"
let hangulGAPrecomposed = "\u{AC00}"
let hangulGAScalars = "\u{1100}\u{1161}"

print(hangulGAPrecomposed == hangulGAScalars)
```

***
## Question 9

**Using only Unicode**, print out `"HELLO WORLD!"`

Answer:
```swift
print("\u{0048}\u{0045}\u{004C}\u{004C}\u{004F}\u{0020}\u{0057}\u{004F}\u{0052}\u{004C}\u{0044}\u{0021}")
```

***
## Question 10

**Using only Unicode**, print out your name.

Answer:
```swift
print("\u{0053}\u{0075}\u{006E}\u{006E}\u{0069}")
```

***
## Question 11

**Using only Unicode**, print out `"HELLO WORLD!"` in another language.

Answer:
```swift
print("\u{00A1}\u{0048}\u{006F}\u{006C}\u{0061}\u{0020}\u{004D}\u{0075}\u{006E}\u{0064}\u{006F}\u{0021}")
```

***
## Question 12

Print the below flower box using the following information.

- The unicode number for ⚘ is U-2698
- The top and bottom of the box are represented by dashes and the rows are |
- Use the terminator argument in your print statements to print on the same line.
- Hint: It may be useful to try printing out a box of just one character to start then work your way from there.

```swift
Flower Box:
- - - - - - - - - - -
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
- - - - - - - - - - -
```
Answer:
```swift

let dash = "\u{0335}"
let line = "\u{01C0}"
let flower = "\u{2698}"

var columnsFlowers = 1...5
var rowsFlowers = 1...7

let upperLowerLines = String(repeating: "\(dash)  ", count:11)

print("Flower Box:")

print(upperLowerLines)

outer: for _ in rowsFlowers {
inner: for _ in columnsFlowers {
print("\(line) \(flower)", terminator: " ")
}
print (line)
}

print(upperLowerLines)
```


***
## Question 13

Write a program that sets up a chess board using Unicode.

```swift
Chess Board:
♖ ♘ ♗ ♕ ♔ ♗ ♘ ♖
♙ ♙ ♙ ♙ ♙ ♙ ♙ ♙




♟ ♟ ♟ ♟ ♟ ♟ ♟ ♟
♜ ♞ ♝ ♛ ♚ ♝ ♞ ♜
```
Answer:

```swift
let column = 1...8
let rowsSpaces = 1...4

print("Chess Board:")
print("\u{2656} \u{2658} \u{2657} \u{2654} \u{2655} \u{2657} \u{2658} \u{2656}")

for _ in column {
print ("\u{2659} ", terminator: "")
}
print("")

outer: for _ in rowsSpaces {
inner: for _ in column {
print("\u{0020}", separator:"", terminator: " ")
}
print("")
}

for _ in column {
print ("\u{265F} ", terminator: "")
}
print("")
print("\u{265C} \u{265E} \u{265D} \u{265B} \u{265A} \u{265D} \u{265E} \u{265C}", terminator: " ")
```

***
## Question 14

You are given a string stored in the variable `aString`. Create new string named `replacedString` that contains the characters of the original string with all the occurrences of the character `"e"` replaced by `"\*"`.

```swift
var aString = "Replace the letter e with \*"
 ```

Example:

Input:
`var aString = "Replace the letter e with *"`

Expected values:
`replacedString = "R*plac* th* l*tt*r * with *"`

Answer:
```swift
var sentence = "Replace the letter e with *"
let sentWithoutE = sentence.replacingOccurrences(of: "e", with: "*", options: .literal, range: nil)

print(sentWithoutE)
```


***
## Question 15

You are given a string stored in variable `aString`. Create a new string called `reverse` that contains the original string in reverse order. Print the reversed string.

```swift
var aString = "this string has 29 characters"
var reverse = ""

// Your code here
```

Example:
Input:
`var aString = "Hello"`

Output:
`"olleH"`

Answer:
```swift
var aString = "this string has 29 characters"
var reverse = String(aString.reversed())

print(reverse)
```

***
## Question 16

You are given a string stored in variable `aString`. Print `true` if `aString` is a palindrome, and `false` otherwise. A **palindrome** is a string which reads the same backward or forward.

```swift
let aString = "anutforajaroftuna"
```

Example 1:
Input:
`var aString = "anutforajaroftuna"`

Output:
`true`

Example 2:
Input:
`var aString = "Hello"`

Output:
`false`

Answer:
```swift
var aString = "anutforajaroftuna"
var reverse = String(aString.reversed())

print(aString == reverse)
```


***
## Question 17

You are given a string stored in variable `problem`. Write code so that you print each word of the string on a new line.

```swift
var problem = "split this string into words and print them on separate lines"
```

Example:
Input:
`var problem ="split this string into words and print them on separate lines"`

Output:
```swift
split
this
string
into
words
and
print
them
on
separate
lines
```
Answer:
```swift
var problem = "split this string into words and print them on separate lines"
var problemArray = problem.components(separatedBy: " ")

for word in problemArray {
print(word)
}
```
***
## Question 18

You are given a string stored in variable `problem`. Write code that prints the longest word in the string.

```swift
var problem = "find the longest word in the problem description"
```

Example:
Input:
`var problem = "find the longest word in the problem description"`

Output:
`description`

Hint: Keep track of the longest word you encounter and also keep track of its length.

Answer:
```swift
var problem = "find the longest word in the problem description"
var problemArray = problem.components(separatedBy: " ")
var longestWord = ""

for word in problemArray {
if longestWord.count < word.count {
longestWord = word
}
}
print(longestWord)
```

***
## Question 19

Given a string in English, create a tuple containing the number of vowels and consonants.

```swift
let vowels = "aeiou"
let consonants = "bcdfghjklmnpqrstvwxyz"
let input = "Count how many vowels I have!"
```
Answer:
```swift
let vowels = "aeiou"
let consonants = "bcdfghjklmnpqrstvwxyz"
let input = "Count how many vowels I have!"

var vowelCount = 0
var conCount = 0

for letter in input.lowercased() {
if vowels.contains(letter) {
vowelCount += 1
} else if consonants.contains(letter) {
conCount += 1
}
}

let tuple = (Vowels: vowelCount, Consonants: conCount)
print(tuple)
```
***
## Question 20

Given a string of words separated by a `" "`. Write code that prints out the length of the last word.

If there is no last word print out `"No last word"`.

Example:
Input: `"How are you doing this Monday?"`

Output: `7`

Answer:
```swift
var string = "How are you doing this Monday?"
var stringArray = string.components(separatedBy: " ")

if string.count != 0 && string != " " {
let lastWord = stringArray.last!
print(lastWord.count)
} else {
print("No last word")
}
```
***
