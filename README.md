# Strings Lab 1

## Instructions for lab submission

1. Fork the assignment repo
1. Clone your Fork to your machine
1. Complete the lab
1. Push your changes to your Fork
1. Submit a Pull Request back to the assignment repo
1. Paste a link to of your Fork on Canvas and submit

## Question 1- 

Write code that prints out all the numbers from 1 to 10 as a single string.
(Hint: the `String()` function can convert an Int to a String)

swift   
***
```
var str = " "

for i in 1...10 {
str += String(i)
}
print(str)
```
## Question 2 -

Write code that prints out all the even numbers from 5 to 51 as a single string.
//
*** 
```
var emptyString = " "
for i in 5...51 where i % 2 == 0 {
emptyString = emptyString + "\(i) "
}
print(emptyString)
```
## Question 3 - 

Write code that prints out every number ending in 4 between 1 and 60 as a single string. 

***
```
var empty = ""
for n in 1...60 {
if n % 10 == 4 {
empty += "\(n) " }
}
print(empty)
```
## Question 4 - 

Print each character in the string `"Hello world!"`

***
```
for c in "Hello world!" {
print(c)
}
```
## Question 5 - done

Print out the last character in the string below.  You cannot use the Character literal "!" (i.e you must access `myStringSeven`'s characters).

`let myStringSeven = "Hello world!"`

***
```
let myStringSeven = "Hello world!"

print(myStringSeven.last!)
```

## Question 6 -

Write code that switches on a string, given the following conditions:
- If the string's length is even, print out every character.
- If the string's length is odd, print out every other character.
***
```
let str = "this is my string!"
let even = str.count % 2 == 0

print("string has a length of: \(str.count)")
switch even {
case true:
for char in str {
print(char, terminator: "")
}
case false:
for index in 0...str.count where index % 2 == 0{
let printIndex = str.index(str.startIndex, offsetBy: index)
print(str[printIndex], terminator: "")
}
}
```

## Question 7 - 

Initialize a String with a character. Show that it is a Character, and not another String, that you're using to initialize it.

***
```
var string = "T"
type(of: string)
Character(string) == Character("T")
```


## Question 8

Build five pairs of **canonically equivalent** strings, the first of each being a pre-composed character and the second being one that uses combinable unicode scalars. Show that they are equivalent. 


***
```
var letterPair = "á"
var letterPairTwo = "a\u{301}"

var anotherLetter = "ì"
var anotherLetterTwo = "i\u{301}"

var symbol = "%"
var symbol1 = "\u{0025}"

var anotherSym = "Ĉ"
var anotherSym1 = "\u{0108}"

var letterBar = "Ʉ"
var letterBar2 = "\u{0244}"
```

## Question 9

**Using only Unicode**, print out `"HELLO WORLD!"`

***
```
var hello = "\u{0048}\u{0045}\u{004c}\u{004c}\u{004f} \u{0057}\u{004f}\u{0052}\u{004c}\u{0044}\u{0021}"

print (hello)
```
## Question 10

**Using only Unicode**, print out your name.
***
```
var myName = "\u{0053}\u{0041}\u{004d}\u{0055}\u{0045}\u{004c}"

print(myName)
```

## Question 11

**Using only Unicode**, print out `"HELLO WORLD!"` in another language.


***
```
var hola = "\u{0048}\u{004f}\u{004c}\u{0041} \u{004d}\u{0055}\u{004e}\u{0044}\u{004f}"

print(hola)
```

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
```
var flower = "\u{2698}"
var verticalSymbol = "\u{007c}"
var horizontalSymbol = "\u{005f}"

for _ in 1...11 {
print(horizontalSymbol, terminator: "")
}
print()
print()
for _ in 1...7 {
print("\(verticalSymbol)\(flower)\(verticalSymbol)\(flower)\(verticalSymbol)\(flower)\(verticalSymbol)\(flower)\(verticalSymbol)\(flower)\(verticalSymbol)")
}
for _ in 1...11 {
print(horizontalSymbol, terminator: "")
}
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
***
```var white = "\u{2656}\u{2658}\u{2657}\u{2655}\u{2654}\u{2657}\u{2658}\u{2656}"
var white2 = "\u{2659}\u{2659}\u{2659}\u{2659}\u{2659}\u{2659}\u{2659}\u{2659}"
var black = "\u{265c}\u{265e}\u{265d}\u{265b}\u{265a}\u{265d}\u{265e}\u{265c}"
var black2 = "\u{265F}\u{265F}\u{265F}\u{265F}\u{265F}\u{265F}\u{265F}\u{265F}"


for  i in white{
print (i, terminator: " ")
}
print()
for i in white2 {
print(i, terminator: " ")
}
for _ in 0...3{
print()
}
for  i in black2{
print (i, terminator: " ")
}
print()
for i in black {
print(i, terminator: " ")
}
```
## Question 14

You are given a string stored in the variable `aString`. Create new string named `replacedString` that contains the characters of the original string with all the occurrences of the character `"e"` replaced by `"\*"`.

```swift
var aString = "Replace the letter e with \*"
// Your code here
 ```

Example:

Input:
`var aString = "Replace the letter e with *"`

Expected values:
`replacedString = "R*plac* th* l*tt*r * with *"`

***
```
var aString = "Replace the letter e with *"
var replacedString = ""

replacedString = aString.replacingOccurrences(of: "e", with: "*")
print (replacedString)
```
## Question 15

You are given a string stored in variable `aString`. Create a new string called `reverse` that contains the original string in reverse order. Print the reversed string.

```
```

Example:
Input:
`var aString = "Hello"`

Output:
`"olleH"`

***
```var aString = "this string has 29 characters"
var reverse = ""

//
reverse += aString.reversed()
print(reverse)
```
## Question 16

You are given a string stored in variable `aString`. Print `true` if `aString` is a palindrome, and `false` otherwise. A **palindrome** is a string which reads the same backward or forward.

```swift

// 
let aString = "anutforajaroftuna"
var reversedString = String(aString.reversed())

if aString == reversedString {
print (true)
}else {
print(false)
}
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

***
## Question 17

You are given a string stored in variable `problem`. Write code so that you print each word of the string on a new line.

```swift
var problem = "split this string into words and print them on separate lines"

var problem2 = problem.components(separatedBy: " ")

for i in problem2 {
print (String(i))
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

***
## Question 18

You are given a string stored in variable `problem`. Write code that prints the longest word in the string.

```swift
var problem = "find the longest word in the problem description"

// var problem = "find the longest word in the problem description"

var seperatedWords = problem.components(separatedBy: " ")
var largestWord = seperatedWords.max(by: { $1.count > $0.count })
if largestWord != nil{
print(largestWord!)
}
```

Example:
Input:
`var problem = "find the longest word in the problem description"`

Output:
`description`

Hint: Keep track of the longest word you encounter and also keep track of its length.

***
## Question 19 -

Given a string in English, create a tuple containing the number of vowels and consonants.

```swift
let vowels = "aeiou"
let consonants = "bcdfghjklmnpqrstvwxyz"
let input = "Count how many vowels I have!"

var alphabet = (vowels.count, consonants.count)

if input = true {
print(vowels.count)
}
```

***
## Question 20 

Given a string of words separated by a `" "`. Write code that prints out the length of the last word.

If there is no last word print out `"No last word"`.

Example:
Input: `"How are you doing this Monday?"`

Output: `7`

***
```
var words = "How are you doing this Monday?"
var lastWord = words.components(separatedBy: " ").last?.count
if lastWord != nil {
print(lastWord!)
}else {
print("no last word")
}
```
