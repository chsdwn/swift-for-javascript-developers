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
