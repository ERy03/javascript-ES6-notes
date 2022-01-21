# JavaScript ES6

### Destructing Objects

Break down object in the following manner:

``` javascript
const player = {
  name: 'Lebron James',
  club: 'LA Lakers',
  address: {
    city: 'Los Angeles'
  }
};
```
How would you normally grab the name of the player? What about the city?

``` javascript
console.log(player.name)
console.log(player.address.city)
```

It's a long syntax 😅
So Instead:

``` javascript
const { name, club, address: {city} } = player;
// This is exactly the same as
// player.name
// player.club
// player.address.city
```

This allows us to access the object key's values in a simpler manner

``` javascript
console.log(name) // Lebron James
console.log(club) // LA Lakers
console.log(city) // Los Angeles
```
<hr>

### Destructuring Arrays

``` javascript
let names = ['Dylan', 'Coding God', 'Israel'];
console.log(names[0]) // Dylan
```

We can destructure the array like this:

``` javascript
let [firstName, middleName, lastName] = ['Dylan', 'Coding God', 'Israel'];
console.log(firstName) // Dylan

// We can override values
firstName = 'Bob'
console.log(firstName) // Bob
```
<hr>

### Object Literals

``` javascript
function addressMaker(city, state) {
  const newAddress = {city: city, state: state}

  console.log(newAddress)
}

addressMaker('Austin', 'Texas')
// {city: "Austin", state: "Texas"}
```

If the keys are the same as the values being passed we don't have to set them.
With object literals:

``` javascript
function addressMaker(city, state) {
  const newAddress = {city, state}

  console.log(newAddress)
}

addressMaker('Austin', 'Texas')
// {city: "Austin", state: "Texas"}
```

Object Literals prevents us from writing duplicate code. Less code but still descriptive.

<hr>

### For of Loop

Can be used to iterate over iterables.

``` javascript
let incomes = [62000, 67000, 75000]
let total = 0

for (const income of incomes) {
  total += income
}

console.log(total) // 204000
```

``` javascript
let name = "Dylan"

for (const char of name) {
  console.log(char)
}

// D
// y
// l
// a
// n
```
<hr>

### Spread Operator

``` javascript
let contacts = ["Mary", "Joel", "Danny"];
let personalFriends = contacts; // copy of contacts

console.log(personalFriends)
// ["Mary", "Joel", "Danny"]

contacts.push("John")
console.log(contacts)
// ["Mary", "Joel", "Danny", "John"]

console.log(personalFriends)
// ["Mary", "Joel", "Danny", "John"]
```

Why is `John` inside of my `personalFriends`?

Because `personalFriends` acts as an reference type. In other words
`let personalFriends = contacts` does not create a new array. Instead it's making a reference to `contacts`. So the changes we make in `contacts` will also affect `personalFriends`.

Then how can we solve this?

-> Spread Operators!

``` javascript
let contacts = ["Mary", "Joel", "Danny"];
let personalFriends = [ ...contacts ];
// spread operator followed by the name of the array we want to copy

contacts.push("John")
console.log(personalFriends)
// ["Mary", "Joel", "Danny"]
```
We can also do the following by using spread operators:

``` javascript
let contacts = ["Mary", "Joel", "Danny"];
let personalFriends = [ "David", ...contacts, "Lily" ];

console.log(personalFriends)
// ["David", "Mary", "Joel", "Danny", "Lily"]
```

Spread operatos can also be used with objects.

``` javascript
let person = {
    name: "Adam",
    age: 25,
    city: "Manchester"
}

let employee = {
    ...person,
    salary: 50000,
    position: "Software Developer"
}

console.log(employee)
// {name: "Adam", age: 25, city: "Manchester", salary: 50000, position: "Software Developer"}
```
<hr>

### Rest Operator

Used when we don't know how many inputs there will be.

``` javascript
function add(nums) {
  console.log(nums)
}

add(4, 5, 7, 8, 12)
// 4

// using arguments
function add(nums) {
  console.log(arguments)
}

add(4, 5, 7, 8, 12)
// {0: 4, 1: 5, 2: 7, 3: 8, 4: 12}
```

Instead of arguments we can use the rest operator which looks liks the spread operator.

``` javascript
function add(...nums) {
  console.log(nums)
}

add(4, 5, 7, 8, 12)
// [ 4, 5, 7, 8, 12 ]
```
<hr>

### Arrow Functions


``` javascript

```
``` javascript

```
``` javascript

```
