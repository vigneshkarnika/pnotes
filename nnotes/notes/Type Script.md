---
title: Type Script
created: '2021-06-10T09:37:23.769Z'
modified: '2021-06-10T16:53:06.020Z'
---

# Type Script
- super set of JS
- static typing(helps us to catch bugs before even run our code)

### JS is Dynamic Typing
```js
let name="john";
name="vignesh"
```

### TS is Static Typing
```js
let name:string="john";
name="vignesh" //error
```
### types
- string
- number
- boolean
- array
- object
- any
- void
- tuple
- enum
- generics
- null
- undefined


```bash
sudo npm i -g typescript
tsc --init
touch app.ts
```
```ts
console.log("hi");
```
```bash
tsc app.ts
```

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <script src="app.js" defer></script>
  </body>
</html>

``` 
- defer specifies that the script is executed when the page has finished parsing.

```ts
let aName = "vignesh";
// implicit string
// if we need to declare variable first 
let aName: string;
aName = 1;//error


let anum=1;
let anum: number;


let abool: boolean
let abool=true;

let anyVar: any
let anyVar;


let year: string | number

const year =parseInt("2021")




let years=[]
let years: any[]=[]
let years=["1","2"]
let years: string[]=["1","2"]

let years: (string | number | boolean)[]
let years=["1","2",4,5,false]
//defeats purpose


let years:[string,boolean]=["1",false]
//index0


let years:[string,boolean]=["1",false]
years=["2",true]

let years:[string,boolean?]=["1",false]
years=["2"]


let person= {
  name:"vignesh",
  age:23,
};
person.name="23";
person.age=2;

//aliases

type numOrStr = number|string
let year:numOrStr;
year="23"
year=23



function add(a:number,b:number){
    return a+b;
}

let res=add(1,2)


function add(a:number,b:number):string{
    return "res:"+a+b;
}


let subtract:(a:number,b:number)=>number;
subtract=(a1:number,b1:number)=>{
    return a1-b1;
}

//void
const sayHi=()=>{
    console.log("hello")
}

let subtract:(a:number,b:number)=>void;
subtract=(a1:number,b1:number)=>{
}



interface PersonInterface {
  name: string;
  age: number;
}

let p1: PersonInterface = {
  name: "vignesh",
  age: 32,
};


class Person implements PersonInterface {
  name: string;
  age: number;
  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }
}



class Person implements PersonInterface {
  name: string;
  age: number;
  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }
  greet() {
    return `hi this is ${this.name} and my age is ${this.age} !`;
  }
}

let vignesh = new Person("vignesh", 32);
console.log(vignesh.greet());



const nameInp=document.querySelector("#name") as HTMLInputElement;
const ageInp=document.querySelector("#age") as HTMLInputElement;
const forInp=document.querySelector("form");
const greetDiv=document.querySelector(".greetdiv") ;


//forminput may not exists
forInp?.addEventListener('submit',()=>{
    
})
//forInp error without ?

const forInp=document.querySelector("form")!;
forInp.addEventListener('submit',()=>{
    
})
//! says exists


```


```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <form>
        <div>name</div>
      <input type="text" name="name" id="name" /></br>
      <div>age</div>
      <input type="number" name="age" id="age" /></br>
      
      <input type="submit" value="say hi!" />
    </form>
    <div class="greetdiv"></div>
    <script src="app.js" defer></script>
  </body>
</html>

```


```ts
const nameInp = document.querySelector("#name") as HTMLInputElement;
const ageInp = document.querySelector("#age") as HTMLInputElement;
const forInp = document.querySelector("form")!;
const greetDiv = document.querySelector(".greetdiv") as HTMLDivElement;

interface PersonInterface {
  name: string;
  age: number;
}
class Person implements PersonInterface {
  name: string;
  age: number;
  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }
  greet() {
    return `hi this is ${this.name} and my age is ${this.age} !`;
  }
}

let vignesh = new Person("vignesh", 32);
console.log(vignesh.greet());

forInp.addEventListener("submit", (e) => {
  e.preventDefault();
  const p2 = new Person(nameInp.value, ageInp.valueAsNumber);
  greetDiv.innerText = p2.greet();
  forInp.reset();
});


function displaySomthing<T>(data:T){
console.log(data);
}

displaySomthing("vignesh")
displaySomthing(1)


displaySomthing<string>("vignesh")
displaySomthing<string>("1")

function displaySomthing<T>(data: T): T {
  console.log(data);
  return data;
}

displaySomthing<PersonInterface>({
    name:"vignesh",
    age:12
});

interface PersonInterface<T> {
    name: string;
    age: T;
  }

displaySomthing<PersonInterface<String>>({
    name:"vignesh",
    age:"32"
});


enum genders {
  Male,
  Female,
  Other,
}

const person = {
  name: "vignesh",
  gender: genders[genders.Male],
};
```
