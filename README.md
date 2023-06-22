# Swift for JavaScript Developers

## Variables

```js
let num = 1
console.log(num) // 1
num = 2
console.log(num) // 2
```
```swift
var num = 1
print(num) // 1
num = 2
print(num) // 2
```

### Constants

```js
const num = 1
console.log(num) // 1
```
```swift
let num = 1
print(num) // 1
```

## Strings

```js
const name = "Ali"
const signature = `
  Signed by ${name}
`
console.log(name.length) // 3
console.log(name.toUpperCase()) // "ALI"
console.log(name.startsWith("Al")) // true
console.log(name.endsWith("li")) // true

console.log("x + " + 1) // "x + 1"
console.log(`2 + 2 = ${2 + 2}`) // "2 + 2 = 4"
```
```swift
let name = "Ali"
let signature = """
  Signed by \(name)
"""
print(name.count) // 3
print(name.uppercased()) // "ALI"
print(name.hasPrefix("Al")) // true
print(name.hasSuffix("li")) // true

print("x + " + String(1)) // x + 1
print("2 + 2 = \(2 + 2)") // 2 + 2 = 4
```

## Numbers

```js
let num = 1_000
num += 1
console.log(num) // 1001

Number.prototype.isMultiple = function({ of = 1 }) {
  return this % of === 0
}
console.log(num.isMultiple({ of: 2 })) // false
console.log(4..isMultiple({ of: 2 })) // true
```
```swift
var num = 1_000
num += 1
print(num) // 1001
print(num.isMultiple(of: 2)) // false
print(4.isMultiple(of: 2)) // true
```

### Decimal Numbers

```js
const num = 0.1 + 0.2
console.log(num) // 0.30000000000000004

let x = 1.5
const y = 2
console.log(x + y) // 3.5
console.log(Math.floor(x) + y) // 3

x *= 2
console.log(x) // 3
```
```swift
let num = 0.1 + 0.2
print(num) // 0.30000000000000004

var x = 1.5
let y = 2
print(x + Double(y)) // 3.5
print(Int(x) + y) // 3

x *= 2
print(x) // 3.0
```

## Booleans

```js
let isAdmin = false
isAdmin = !isAdmin
console.log(isAdmin) // true
```
```swift
var isAdmin = false
isAdmin = !isAdmin
print(isAdmin) // true

isAdmin.toggle()
print(isAdmin) // false
```

## Arrays

```js
const numbers = [1, 2, 3]
numbers.push(4)

const names = new Array()
names.push("Ali")
console.log(names[0]) // "Ali"

const grades = []
grades.push(73)

let alphabet = ["a", "b", "c", "d"]
console.log(alphabet.length) // 4
console.log(alphabet.splice(2, 1)) // ["c"]
alphabet.length = 0

alphabet = ["c", "a", "d", "b"]
console.log(alphabet.includes("e")) // false
console.log([...alphabet].sort()) // ["a", "b", "c", "d"]
console.log([...alphabet].reverse()) // ["b", "d", "a", "c"]
```
```swift
var numbers = [1, 2, 3]
numbers.append(4)

var names = Array<String>()
names.append("Ali")
print(names[0]) // "Ali"

var grades = [Int]()
grades.append(73)

var alphabet: [String] = ["a", "b", "c", "d"]
print(alphabet.count) // 4
print(alphabet.remove(at: 2)) // "c"
alphabet.removeAll()

alphabet = ["c", "a", "d", "b"]
print(alphabet.contains("e")) // false
print(alphabet.sorted()) // ["a", "b", "c", "d"]
print(alphabet.reversed()) // ReversedCollection<Array<String>>(_base: ["c", "a", "d", "b"])
```

## Dictionaries

```js
const ali = {
  name: "Ali",
  surname: "Veli",
  age: "20",
}
console.log(ali.name) // "Ali"
console.log(ali.surname) // "Veli"
console.log(ali.age) // "20"

const olympics = new Map()
olympics.set(2012, "London")
olympics.set(2016, "Rio")
olympics.set(2016, "Rio de Janeiro")
olympics.set(2021, "Tokyo")
console.log(olympics.get(2012)) // "London"
console.log(olympics.size) // 3
```
```swift
let ali = [
  "name": "Ali",
  "surname": "Veli",
  "age": "20",
]
print(ali["name", default: "Unknown"]) // Optional("Ali")
print(ali["surname", default: "Unknown"]) // Optional("Veli")
print(ali["age", default: "Unknown"]) // Optional("20")

var olympics = [Int: String]()
olympics[2012] = "London"
olympics[2016] = "Rio"
olympics[2016] = "Rio de Janeiro"
olympics[2021] = "Tokyo"
print(olympics[2012, default: "World"]) // Optional("London")
print(olympics.count) // 3
```

## Sets

```js
const names = new Set(["Ali", "Veli", "Ahmet"])
console.log(names) // Set { "Ali", "Veli", "Ahmet" }

const cities = new Set()
cities.add("İstanbul")
cities.add("İstanbul")
console.log(cities.has("İstanbul")) // true
console.log(cities.size) // 1
cities.add("Ankara")
console.log(Array.from(cities).sort()) // ["Ankara", "İstanbul"]
```
```swift
let names = Set(["Ali", "Veli", "Ahmet"])
print(names) // ["Ali", "Veli", "Ahmet"]

var cities = Set<String>()
cities.insert("İstanbul")
cities.insert("İstanbul")
print(cities.contains("İstanbul")) // true
print(cities.count) // 1
cities.insert("Ankara")
print(cities.sorted()) // ["Ankara", "İstanbul"]
```

## Enums

```js
const Weekday = Object.freeze({
  monday: Symbol("monday"),
  tuesday: Symbol("tuesday"),
  wednesday: Symbol("wednesday"),
  thursday: Symbol("thursday"),
  friday: Symbol("friday"),
})
```
```swift
enum Weekday {
  case monday
  case tuesday
  case wednesday
  case thursday
  case friday
}
var day = Weekday.monday
day = Weekday.tuesday
day = .wednesday

enum Weekend {
  case saturday, sunday
}
```

## Type Annonations

```ts
const name: string = "Ali"
const score: number = 0
const pi: number = 3.141
const isAdmin: boolean = true
const albums: string[] = ["Century Child", "Human. :II: Nature."]
const olympics: Map<number, string> = new Map([
  [2012, "London"],
  [2016, "Rio"],
  [2021, "Tokyo"],
])
const books: Set<string> = new Set(["The Name of the Wind", "The Wise Man's Fear"])
```
```swift
let name: String = "Ali"
let score: Double = 0
let pi: Double = 3.141
let isAdmin: Bool = true
let albums: [String] = ["Century Child", "Human. :II: Nature."]
let olympics: [Int: String] = [2012: "London", 2016: "Rio", 2021: "Tokyo"]
let books: Set<String> = Set(["The Name of the Wind", "The Wise Man's Fear"])
```

## Conditions

### `if`/`else`

```js
const age = 18
const isAdmin = true
if (age >= 18 && isAdmin) {
  console.log("You're authenticated")
} else if (age < 18) {
  console.log("You're not an adult")
} else if (!isAdmin) {
  console.log("Contact with an admin")
} else {
  console.log("You're unauthenticated")
}
```
```swift
let age = 18
let isAdmin = true
if age >= 18 && isAdmin {
  print("You're authenticated")
} else if age < 18 {
  print("You're not an adult")
} else if !isAdmin {
  print("Contact with an admin")
} else {
  print("You're unauthenticated")
}
```

### `switch`/`case`

```js
const num = 2
switch (num) {
  case 1:
    console.log("one")
    break
  case 2:
    console.log("two") // "two"
  case 3:
    console.log("three") // "three"
  default:
    console.log("4,5,6,...") // "4,5,6,..."
}
```
```swift
let num = 2
switch num {
case 1:
  print("one")
case 2:
  print("two") // "two"
  fallthrough
case 3:
  print("three") // "three"
  fallthrough
default:
  print("4,5,6,...") // "4,5,6,..."
}
```

### Ternary Conditional Operator: `?:`

```js
const age = 18
const canVote = age >= 18 ? "Y" : "N"
console.log(canVote) // "Y"
```
```swift
let age = 18
let canVote = age >= 18 ? "Y" : "N"
print(canVote) // "Y"
```

## Loops

### `for` Loop

```js
const alphabet = ["a", "b", "c"]
for (const char of alphabet) {
  console.log(char) // "a", "b", "c"
}

const range = (from, to, { inclusive = true } = {}) => 
  Array(to - from + Number(inclusive)).fill(null).map((_, i) => i + from)
// range(3, 5) = 3...5
for (const num of range(3, 5)) {
  if (num === 5) break
  if (num % 2 === 1) continue
  console.log(num) // 2, 4
}
// range(3, 5, { inclusive: false }) = 3..<5
for (const num of range(3, 5, { inclusive: false })) {
  console.log(num) // 3, 4
}
```
```swift
let alphabet = ["a", "b", "c"]
for char in alphabet {
  print(char) // "a", "b", "c"
}

for num in 1...10 {
  if num == 5 {
    break
  }
  if num % 2 == 1 {
    continue
  }
  print(num) // 2, 4
}
for num in 3..<5 {
  print(num) // 3, 4
}
```

### `while` Loop

```js
let num = 0
while (num !== 4) {
  num = Math.ceil(Math.random() * 10)
  console.log(num) // 1 to 10
}
```
```swift
var num = 0
while num != 4 {
  num = Int.random(in: 1...10)
  print(num) // 1 to 10
}
```

## Functions

```js
const isEven = ({ num }) => {
  const res = num % 2 === 0
  return res
}
console.log(isEven({ num: 3 })) // false
```
```swift
func isEven(num: Int) -> Bool {
  let res = num % 2 == 0
  return res
}
print(isEven(num: 3)) // false
```

### Return Multiple Values

```js
const getUserArray = () => ["Floor", "Jansen"]
const userArray = getUserArray()
console.log(`${userArray[0]} ${userArray[1]}`) // "Floor Jansen"

const getUserDict = () => ({ name: "Floor", surname: "Jansen" })
const userDict = getUserDict()
console.log(`${userDict.name} ${userDict.surname}`) // "Floor Jansen"

const getUserTuple = () => ["Floor", "Jansen"]
const userTuple = getUserTuple()
console.log(`${userArray[0]} ${userArray[1]}`) // "Floor Jansen"

const getUserNamedTuple = () => ({ name: "Floor", surname: "Jansen" })
const { name, surname } = getUserNamedTuple()
console.log(`${name} ${surname}`) // "Floor Jansen"
```
```swift
func getUserArray() -> [String] {
  ["Floor", "Jansen"]
}
let userArray = getUserArray()
print("\(userArray[0]) \(userArray[1])") // "Floor Jansen"

func getUserDict() -> [String: String] {
  ["name": "Floor", "surname": "Jansen"]
}
let userDict = getUserDict()
print("\(userDict["name", default: "Ali"]) \(userDict["surname", default: "Veli"])") // "Floor Jansen

func getUserTuple() -> (String, String) {
  ("Floor", "Jansen")
}
let userTuple = getUserTuple()
print("\(userTuple.0) \(userTuple.1)") // "Floor Jansen"

func getUserNamedTuple() -> (name: String, surname: String) {
  // ("Floor", "Jansen") // This is valid also
  (name: "Floor", surname: "Jansen")
}
let (name, _) = getUserNamedTuple()
let (_, surname) = getUserNamedTuple()
print("\(name) \(surname)") // "Floor Jansen"
```

### Customize Parameter Labels

```js
const isOdd = (num) => {
  return num % 2 === 1
}
console.log(isOdd(3)) // true

const printTimesTable = ({ for: num }) => {
  for (let i = 1; i <= 3; i++) {
    console.log(`${i} x ${num} = ${i * num}`)
  }
}
printTimesTable({ for: 5 }) // "1 x 5 = 5", "2 x 5 = 10", "3 x 5 = 15"
```
```swift
func isOdd(_ num: Int) -> Bool {
  num % 2 == 1
}
print(isOdd(3)) // true

func printTimesTable(for num: Int) {
  for i in 1...3 {
    print("\(i) x \(num) = \(i * num)")
  }
}
printTimesTable(for: 5) // "1 x 5 = 5", "2 x 5 = 10", "3 x 5 = 15"
```

### Default Values for Parameters

```js
const printNumbers = ({ from, to = 10 }) => {
  for (let i = from; i <= to; i++) console.log(i)
}
printNumbers({ from: 8 }) // 8, 9, 10
```
```swift
func printNumbers(from: Int, to: Int = 10) {
  for i in from...to {
    print(i)
  }
}
printNumbers(from: 8) // 8, 9, 10
```

### Handle Errors in Functions

```js
const PasswordError = Object.freeze({
  short: Symbol("short"),
  obvious: Symbol("obvious"),
})

const checkPassword = (password) => {
  const length = password.length
  if (length < 5) throw PasswordError.short
  if (password === "12345") throw PasswordError.obvious

  if (length < 8) return "Ok"
  if (length < 10) return "Good"
  return "Excellent"
}

try {
  const res = checkPassword("12345")
  console.log(res)
} catch (err) {
  if (err === PasswordError.short) {
    console.log("Short password")
  } else if (err === PasswordError.obvious) {
    console.log("Try a stronger password.") // "Try a stronger password."
  } else {
    console.log("An error occured.")
  }
}
```
```swift
enum PasswordError: Error {
  case short, obvious
}

func checkPassword(_ password: String) throws -> String {
  let count = password.count
  if count < 5 {
    throw PasswordError.short
  }

  if password == "12345" {
    throw PasswordError.obvious
  }

  if count < 8 {
    return "Ok"
  } 
  if count < 10 {
    return "Good"
  }
  return "Excellent"
}

do {
  let res = try checkPassword("12345")
  print(res)
} catch PasswordError.short {
  print("Short password")
} catch PasswordError.obvious {
  print("Try a stronger password.") // "Try a stronger password."
} catch {
  print("An error occured")
}
```
