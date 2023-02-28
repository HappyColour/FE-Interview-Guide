# FE-Interview-Guide
2023前端面试、2023前端面试指南、前端面试、前端面试指南

1. Javascript

  ① 数据类型：原始数据类型 & 引用数据类型
  原始数据类型：number string boolean symbol null undefined
  引用数据类型：对象 数组 函数

  I 函数：
  函数是一种重要的语言特性，可以被用于封装可重用的代码，实现逻辑复杂的功能，并提供一种结构化的编程方式。

  函数定义：
  函数定义可以使用函数声明或函数表达式的形式来创建。

  函数声明：
  函数声明通常是以function关键字开头，后跟函数名和一对圆括号，再加上一对花括号来定义函数体。例如：
      function add(a, b) {
        return a + b
      }
  
  函数表达式：
  函数表达式通常是将函数定义赋值给变量，或作为参数传递给其他函数。例如：
      const add = (a, b) => { return a + b }

  函数调用：
  函数调用是指在函数名称后面加上一对圆括号，传递参数给函数。例如：
      const result = add(3, 3); // return 6
  
  参数传递：
  参数传递是指函数可以接受任意数量的参数，这些参数可以是原始类型、对象或其他函数。例如：
      const infor = {
        name: 'Danny',
        age: '18'
      }
      const reduceResult = (c, d) => { return c - d }
      function greet(name, obj, result) {
        console.log(`Hello，${name}!!!`)
        console.log(`${obj.age} Forever!`)
        console.log(result)
      }
      greet('Danny', infor, reduceResult(12, 6)) // Hello，Danny!!!，18 Forver!，6
  
  返回值：
  函数可以通过return语句返回一个值，也可以不返回任何值（返回undefined）。

  作用域：
  函数可以访问在函数定义外部定义的变量，这些变量被称为全局变量。但是在函数内部定义的变量只能在函数内部访问，这些变量被称为局部变量。例如：
      const x = 10;
      function foo() {
        const y = 20;
        console.log(x); // 输出10
        console.log(y); // 输出20
      }
      foo();
      console.log(x); // 输出10
      console.log(y); // ReferenceError: y is not defined
  
  高阶函数：
  函数可以作为参数传递给其他函数，或从函数中返回另一个函数。这种函数被称为高阶函数。例如：
      function operation(a, b, func) {
        return func(a, b);
      }
      const result = operation(2, 3, function(a, b) {
        return a + b;
      }); // result的值为5

  II 对象：
  对象是一种非常重要的数据类型，它是一组无需的属性和值的集合，属性名必须是字符串类型。

  对象定义：
  对象可以使用字面量、构造函数Object.create()方法来创建。字面量定义是最常用的方式，它使用一对花括号包含属性和值的键值对，属性名和属性值之间用冒号分隔，每个键值对之间用逗号分隔。例如：
      const person = {
        name: 'Danny',
        age: 18,
        address: {
          street: 'Chao Yang Street',
          city: 'Beijing',
          country: 'China'
        }
      }

  对象访问：
  对象的属性可以使用点号或方括号来访问。例如：
  console.log(person.name); // print 'Danny'
  console.log(person['age']); // print 18

  对象方法：
  对象的属性可以是函数，这种属性被称为对象方法。例如：
      const person = {
        name: 'Danny',
        greet: function(){
          console.log(`Hello，my name is ${this.name}！`)
        }
      }
      person.greet(); // print "Hello，my name is Danny！"
  
  对象遍历：可以使用for...in循环或Object.keys()方法来遍历对象的属性。例如：
      for(const key in person) {
        console.log(`${key}：${person[key]}`)
      }
      const keys = Object.keys(person)
      console.log(keys)

  对象复制：可以使用Object.assign()方法来复制对象。例如：
      const person2 = Object.assign({}, person)
      person2.name = 'Choco'
      console.log(person.name) // print 'Danny'
      console.log(person2.name) // print 'Choco'
  
  III 数组：
  数组是一种非常重要的数据类型，它是一组有序的值的集合，每个值可以是任意数据类型，包括数字、字符串、布尔值、对象、函数等。

  数组定义：
  数组可以使用字面量或Array构造函数来创建。字面量定义是最常用的方式，它使用一对方括号包含数组中的值，每个值之间用逗号分隔。例如：
      const numbers = [1,2,3,4,5]
  
  数组访问：
  可以使用下标（索引）来访问数组中的元素，数组的下标从0开始。例如：
      console.log(numbers[0]) // print 1
      console.log(numbers[2]) // print 3
  
  数组方法：
  数组提供了很多常用的方法，例如push()、pop()、shift()、unshift()、slice()、splice()、concat()、join()、reverse()等。这些方法可以对数组进行增删改查等操作。例如：
      const fruits = ['apple','banana','orange']
      fruits.push('pear')
      console.log(fruits) // ['apple','banana','orange','pear']
      fruits.pop()
      console.log(fruits) // ['apple','banana','orange']
      fruits.splice(1,1,'grape','kiwi')
      console.log(fruits) // ['apple','grape','kiwi','orange']
  
  push()：在数组末尾添加一个或多个元素，并返回新数组的长度。
      const arr = [1, 2, 3];
      const length = arr.push(4, 5);
      console.log(arr); // [1, 2, 3, 4, 5]
      console.log(length); // 5
  pop()：从数组末尾删除一个元素，并返回该元素的值。
      const arr = [1, 2, 3];
      const value = arr.pop();
      console.log(arr); // [1, 2]
      console.log(value); // 3
  shift()：从数组开头删除一个元素，并返回该元素的值。
      const arr = [1, 2, 3];
      const value = arr.shift();
      console.log(arr); // [2, 3]
      console.log(value); // 1
  unshift()：在数组开头添加一个或多个元素，并返回新数组的长度。
      const arr = [1, 2, 3];
      const length = arr.unshift(0, -1);
      console.log(arr); // [0, -1, 1, 2, 3]
      console.log(length); // 5
  slice()：返回一个新数组，从原数组中指定的开始索引到结束索引（不包括结束索引）。
      const arr = [1, 2, 3, 4, 5];
      const newArr = arr.slice(1, 4);
      console.log(newArr); // [2, 3, 4]
  splice()：从数组中删除或添加元素，并返回被删除的元素。
      const arr = [1, 2, 3, 4, 5];
      const deletedArr = arr.splice(1, 2, 6, 7);
      console.log(arr); // [1, 6, 7, 4, 5]
      console.log(deletedArr); // [2, 3]
  concat()：将两个或多个数组合并成一个新数组。
      const arr1 = [1, 2, 3];
      const arr2 = [4, 5, 6];
      const newArr = arr1.concat(arr2);
      console.log(newArr); // [1, 2, 3, 4, 5, 6]
  join()：将数组中的所有元素转换为字符串，并使用指定的分隔符连接起来。
      const arr = [1, 2, 3];
      const str = arr.join('-');
      console.log(str); // '1-2-3'
  reverse()：将数组中的元素顺序颠倒。
      const arr = [1, 2, 3];
      arr.reverse();
      console.log(arr); // [3, 2, 1]
  forEach()：对数组中的每个元素执行指定的操作。
      const arr = [1, 2, 3];
      arr.forEach((item, index) => {
        console.log(`index=${index}, item=${item}`);
      });
      // 输出：
      // index=0, item=1
      //
  map()：对数组中的每个元素执行指定的操作，并返回操作后的新数组。
      const arr = [1, 2, 3];
      const newArr = arr.map((item, index) => {
        return item * index;
      });
      console.log(newArr); // [0, 2, 6]
  filter()：根据指定的条件过滤数组中的元素，并返回符合条件的新数组。
      const arr = [1, 2, 3, 4, 5];
      const newArr = arr.filter((item) => {
        return item % 2 === 0;
      });
      console.log(newArr); // [2, 4]
  reduce()：对数组中的每个元素执行指定的操作，并返回一个累加器的结果。
      const arr = [1, 2, 3, 4, 5];
      const result = arr.reduce((accumulator, currentValue) => {
        return accumulator + currentValue;
      });
      console.log(result); // 15
  some()：判断数组中是否存在符合指定条件的元素，如果存在则返回true，否则返回false。
      const arr = [1, 2, 3, 4, 5];
      const hasEvenNumber = arr.some((item) => {
        return item % 2 === 0;
      });
      console.log(hasEvenNumber); // true
  every()：判断数组中的所有元素是否都符合指定的条件，如果都符合则返回true，否则返回false。
      const arr = [1, 2, 3, 4, 5];
      const allEvenNumber = arr.every((item) => {
        return item % 2 === 0;
      });
      console.log(allEvenNumber); // false

  数组遍历：
  可以使用for循环、forEach()方法、map()方法等来遍历数组中的元素。例如：
      for(let i = 0;i < fruits.length; i++) { 
        console.log(fruits[i]) 
      }
      fruits.forEach(function(item, index){ 
        console.log(`${index}：${item}`)
      })
      const newFruits = fruits.map(function(item) {
        return item.toUpperCase();
      });
      console.log(newFruits); // 输出 ["APPLE", "GRAPE", "KIWI", "ORANGE"]
  
  数组复制：
  可以使用slice()方法或扩展运算符（...）来复制数组。例如：
      const newNumbers = numbers.slice();
      newNumbers[0] = 100;
      console.log(numbers); // 输出 [1, 2, 3, 4, 5]
      console.log(newNumbers); // 输出 [100, 2, 3, 4, 5]

      const newFruits = [...fruits];
      newFruits[0] = 'pear';
      console.log(fruits); // 输出 ["apple", "grape", "kiwi", "orange"]
      console.log(newFruits); // 输出 ["pear", "grape", "kiwi", "orange"]
  
  面向对象编程：
  JavaScript 是一种面向对象的编程语言，它采用了基于原型的面向对象编程范式。在 JavaScript 中，所有的对象都有一个原型，它们从其原型中继承属性和方法。这种基于原型的面向对象编程方式与基于类的面向对象编程方式不同。

  JavaScript 中的对象可以通过构造函数来创建，构造函数是一种特殊的函数，用于创建新对象并设置其属性和方法。在构造函数中使用 this 关键字来定义对象的属性和方法，这些属性和方法可以通过 new 关键字来实例化并调用。

  例如，我们可以定义一个名为 Person 的构造函数，用于创建人员对象：

      function Person(name, age) {
        this.name = name;
        this.age = age;
        this.greet = function() {
          console.log(`Hello, my name is ${this.name} and I'm ${this.age} years old.`);
        };
      }

  上述代码中，Person 构造函数接受两个参数 name 和 age，并将它们赋值给 this 对象的 name 和 age 属性。同时，Person 构造函数还定义了一个 greet 方法，用于向控制台输出人员信息。

  我们可以使用 new 关键字来实例化一个 Person 对象，并调用它的 greet 方法：

      const john = new Person('John', 25);
      john.greet(); // 输出 "Hello, my name is John and I'm 25 years old."

  在 JavaScript 中，我们还可以使用原型继承来创建对象之间的关系。每个对象都有一个 __proto__ 属性，它指向该对象的原型。通过修改原型对象，我们可以添加属性和方法，并使其在所有实例之间共享。

  例如，我们可以向 Person 的原型对象中添加一个 sayHi 方法：

      Person.prototype.sayHi = function() {
        console.log(`Hi, my name is ${this.name}.`);
      };

  现在，我们可以通过 john 对象来调用 sayHi 方法：

  john.sayHi(); // 输出 "Hi, my name is John."

  除了原型继承，JavaScript 还支持通过 class 关键字创建类。类是一种语法糖，它基于原型继承，让面向对象编程更加直观和易读。

  例如，我们可以使用 class 关键字来定义一个 Person 类：

      class Person {
        constructor(name, age) {
          this.name = name;
          this.age = age;
        }
        
        greet() {
          console.log(`Hello, my name is ${this.name} and I'm ${this.age} years old.`);
        }
        
        static sayHi() {
          console.log('Hi, there.');
        }
      }
  上述代码中，Person 类包含一个构造函数和两个实例方法：greet 和一个静态方法 sayHi。

  我们可以使用 new 关键字来实例化一个 Person

  对象：JavaScript 中的对象是一种复合数据类型，它可以包含任意数量的属性和方法。对象的属性可以是基本类型（如字符串、数字等）或其他对象。创建对象的方式包括对象字面量、构造函数和 Object.create 方法等。
  原型：每个对象都有一个原型，原型对象包含了该对象的属性和方法，并且它也可以有自己的原型。通过原型链，JavaScript 对象可以从其他对象继承属性和方法。
  继承：JavaScript 中的继承是通过原型链实现的。当一个对象需要继承另一个对象的属性和方法时，它可以将另一个对象作为它的原型。JavaScript 还提供了一些内置方法，如 Object.create 和 Object.setPrototypeOf，用于设置对象的原型。
  构造函数：在 JavaScript 中，构造函数是一种特殊的函数，用于创建新的对象并设置它的属性和方法。构造函数使用 this 关键字来引用正在创建的对象，并且通常使用 new 关键字来实例化对象。
  类：在 ES6 中，JavaScript 引入了类的概念，使面向对象编程更加直观和易读。类是一种语法糖，它基于原型继承，让面向对象编程更加直观和易读。

  深拷贝：
  在 JavaScript 中，对象和数组是引用类型，即它们的值实际上是存储在内存中的地址。因此，在进行对象和数组的复制时，只是将它们的引用复制了一份，而不是将它们的值复制一份，这就是浅拷贝（shallow copy）。浅拷贝有时会导致意外的结果，因为对原始对象或数组的更改会影响所有引用该对象或数组的变量。

  为了解决这个问题，可以使用深拷贝（deep copy）来创建一个完全独立于原始对象或数组的副本。深拷贝会递归地复制对象或数组中的所有属性和元素，并将它们的值复制一份。这样，即使对原始对象或数组进行更改，也不会影响复制后的对象或数组。

  以下是几种实现深拷贝的方法：

  1. 使用 JSON.stringify 和 JSON.parse：JSON.stringify 可以将 JavaScript 对象或数组转换为 JSON 字符串，JSON.parse 可以将 JSON 字符串转换为 JavaScript 对象或数组。这种方法的缺点是，它无法处理函数和循环引用。
  
      const originalObj = { a: 1, b: { c: 2 } };
      const copiedObj = JSON.parse(JSON.stringify(originalObj));
  
  2. 使用递归函数：递归函数可以遍历对象或数组中的所有属性和元素，并递归地复制它们。这种方法可以处理函数和循环引用。

      function deepClone(obj) {
        if (typeof obj !== "object" || obj === null) {
          return obj;
        }

        const newObj = Array.isArray(obj) ? [] : {};

        for (let key in obj) {
          newObj[key] = deepClone(obj[key]);
        }

        return newObj;
      }

      const originalObj = { a: 1, b: { c: 2 } };
      const copiedObj = deepClone(originalObj);

  3. 使用第三方库：许多第三方库，如 lodash、jQuery 等，都提供了实现深拷贝的方法。这些方法通常支持函数、循环引用和其他特殊情况。

    const originalObj = { a: 1, b: { c: 2 } };
    const copiedObj = _.cloneDeep(originalObj);

  需要注意的是，深拷贝可能会很慢，尤其是对于大型的对象和数组。因此，在实际使用中，需要根据具体情况选择合适的方法来进行拷贝。

  原型链：
  在 JavaScript 中，每个对象都有一个内部属性称为原型（prototype），它指向另一个对象，这个对象也可能有自己的原型，形成了一个原型链（prototype chain）。

  当访问一个对象的属性或方法时，如果这个对象本身没有这个属性或方法，JavaScript 引擎会沿着这个对象的原型链向上查找，直到找到该属性或方法或者到达原型链的顶部（即 Object.prototype）。如果没有找到，就会返回 undefined。

  以下是一个简单的例子，说明原型链的工作方式：

      function Person(name, age) {
        this.name = name;
        this.age = age;
      }

      Person.prototype.sayHello = function() {
        console.log(`Hello, my name is ${this.name}`);
      };

      const john = new Person("John", 30);

      john.sayHello(); // 输出 "Hello, my name is John"

      console.log(john.hasOwnProperty("name")); // 输出 true
      console.log(john.hasOwnProperty("sayHello")); // 输出 false

  在这个例子中，我们创建了一个 Person 构造函数，并将它的原型添加了一个 sayHello 方法。当我们创建一个名为 john 的 Person 对象时，它继承了 Person 构造函数的属性和方法，并且它的原型指向了 Person.prototype。

  当我们调用 john 的 sayHello 方法时，JavaScript 引擎会先检查 john 对象本身是否有这个方法，如果没有，它就会沿着 john 对象的原型链向上查找，并找到了 Person.prototype 上的 sayHello 方法。

  当我们使用 hasOwnProperty 方法检查 john 对象是否有 name 和 sayHello 属性时，它会返回 true 和 false。这是因为 name 是 john 对象本身的属性，而 sayHello 是继承自原型链上的属性。

  总之，原型链是 JavaScript 中实现继承的机制之一，它允许对象继承另一个对象的属性和方法，并且可以形成一个层级结构，使得继承关系变得清晰和可维护。






