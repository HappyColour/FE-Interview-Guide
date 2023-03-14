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
  注：Object.assign()一级是深拷贝，除外是浅拷贝。
  
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
  slice和concat这两个方法，仅适用于对不包含引用对象的一维数组的深拷贝

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

  深拷贝应用场景：
  1. 对象拷贝：在需要复制一个对象的同时不改变原对象的情况下使用深拷贝。如果使用浅拷贝，复制得到的新对象只是原对象的引用，修改新对象时也会影响原对象。
  2. 配置文件：在配置文件中存储了一些数据，需要将这些数据进行深拷贝以便在代码中使用，以免改变原配置数据。
  3. 缓存数据：在缓存中存储了一些数据，需要将这些数据进行深拷贝以便在使用时可以避免修改原缓存数据。
  4. 嵌套数据的处理：当有多层嵌套的数据时，需要进行深拷贝以保持数据结构的完整性。
  5. 数据备份：在对一些重要数据进行备份时，需要使用深拷贝以确保备份数据与原数据相互独立。
  6. 数据传递：在使用某些函数或模块传递数据时，需要使用深拷贝以确保数据在传递时不会被修改。
  7. 多级菜单：在使用多级菜单时，需要进行深拷贝以保持菜单结构的完整性。
  8. 递归数据结构的处理：当处理递归数据结构时，需要使用深拷贝以避免递归陷阱。

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

  闭包：
  闭包（closure）是指一个函数能够访问并“记住”其词法作用域（lexical scope）中的变量，即使这个函数在它的词法作用域之外被执行。

  具体来说，当一个函数在另一个函数内部定义时，并且它引用了外部函数的变量或参数，就形成了一个闭包。这个闭包包含了这个内部函数以及它所引用的外部函数变量或参数的引用。在函数执行完毕后，这些外部变量或参数的值不会被销毁，而是一直保存在这个闭包中，直到闭包被销毁。

  以下是一个简单的例子，说明闭包的工作方式：
      function outerFunction(x) {
        function innerFunction(y) {
          return x + y;
        }
        return innerFunction;
      }

      const add5 = outerFunction(5);
      console.log(add5(3)); // 输出 8
      console.log(add5(7)); // 输出 12
  在这个例子中，我们定义了一个名为 outerFunction 的函数，它返回了一个内部函数 innerFunction。当我们调用 outerFunction(5) 时，它会创建一个闭包，将外部函数的参数 x 的值保存在内部函数中，并将内部函数返回。当我们调用 add5(3) 时，它会在闭包中查找 x 的值，将 3 与 5 相加并返回 8。当我们调用 add5(7) 时，它会在同一个闭包中查找 x 的值，并将 7 与 5 相加并返回 12。因此，add5 实际上是一个闭包，它“记住”了外部函数的参数 x 的值，使我们可以在多次调用之间保持状态。

  闭包在 JavaScript 中有广泛的应用，例如实现私有变量、模块化编程、异步编程等。但是在使用闭包时需要小心，因为它们可能会导致内存泄漏或性能问题，尤其是当闭包长时间存在或引用了大量变量时。

  闭包应用场景：
  1. 实现模块化：通过闭包，可以将一些私有变量和方法封装在模块内部，避免与全局命名空间产生冲突。
  2. 延迟执行：通过将需要延迟执行的代码封装在闭包中，可以在需要时再执行。
  3. 保存状态：闭包可以保存函数执行时的状态，使得函数在执行时能够访问到之前的状态。
  4. 函数柯里化：通过闭包，可以将一个多参数函数转换为一个单参数的函数，方便部分参数的传递。
  5. 防抖和节流：通过闭包和定时器，可以实现防抖和节流的效果，避免频繁触发事件。
  6. 实现私有变量和方法：通过闭包，可以将一些变量和方法隐藏在函数作用域中，不被外部访问。
  7. 缓存计算结果：通过闭包，可以将一些计算结果缓存起来，避免重复计算。
  8. 实现回调函数：通过闭包，可以将函数作为参数传递给其他函数，并在其他函数执行完毕后调用。
  以上这些应用场景只是闭包的一部分，实际上闭包还有很多其他的应用，如实现事件委托、处理异步回调等。通过合理的使用闭包，可以让代码更加简洁、优雅和高效。

  Promise：
  Promise 是一种用于处理异步操作的机制，它通过 then() 方法和 catch() 方法来处理异步操作成功和失败的结果。
  当创建一个 Promise 对象时，它的状态会从 pending（等待状态）变为 fulfilled（成功状态）或 rejected（失败状态）其中之一，这取决于异步操作的结果。如果异步操作成功，Promise 对象就会变为 fulfilled 状态，并且可以通过 then() 方法获取到异步操作的结果；如果异步操作失败，Promise 对象就会变为 rejected 状态，并且可以通过 catch() 方法获取到错误信息。

  1. AJAX请求
      function getData(url) {
        return new Promise(function(resolve, reject){
          const xhr = new XMLHttpRequest()
          xhr.open('GET', url)
          xhr.onreadystatechange = function(){
            if(xhr.readyState === 4 && xhr.status === 200) {
              resolve(xhr.responseText)
            }else {
              reject(xhr.status)
            }
          }
          xhr.send()
        })
      }
      getData('https://jsonplaceholder.typicode.com/todos/1')
        .then(function(response) {
          console.log('Success:', response);
        })
        .catch(function(error) {
          console.error('Error:', error);
        });
  2. 定时器
      function delay(time) {
        return new Promise(function(resolve, reject) {
          setTimeout(resolve, time)
        })
      }
      console.log('Start')
      delay(1000).then(function(){
        console.log('1 second later')
        return delay(2000)
      }).then(function(){
        console.log('2 seconds later')
        return delay(3000)
      }).then(function(){
        console.log('3 seconds later')
        console.log('End')
      })
  3. 多个异步操作顺序执行
      function task1() {
        return new Promise(function(resolve, reject) {
          console.log('Task 1 start');
          setTimeout(function() {
            console.log('Task 1 end');
            resolve();
          }, 1000);
        });
      }
      function task2() {
        return new Promise(function(resolve, reject) {
          console.log('Task 2 start');
          setTimeout(function() {
            console.log('Task 2 end');
            resolve();
          }, 2000);
        });
      }
      function task3() {
        return new Promise(function(resolve, reject) {
          console.log('Task 3 start');
          setTimeout(function() {
            console.log('Task 3 end');
            resolve();
          }, 3000);
        });
      }
      task1()
        .then(task2)
        .then(task3)
        .then(function() {
          console.log('All tasks completed');
        });

  4. Promise.all
      const getAllData = async () => {
        const url = 'https://jsonplaceholder.typicode.com/todos'
        try {
          let responses = await Promise.all([fetch(`${url}/1`), fetch(`${url}/2`), fetch(`${url}/3`)])
          console.log('responses', responses)
          let jsons = responses.map(response => response.json())
          console.log('jsons', jsons)
          let values = await Promise.all(jsons)
          values.map(value => {
            console.log(value.title)
          })
        } catch (err) {
          console.log(err)
        }
      }
      getAllData()
   
  async/await：
  async/await 是基于 Promise 的语法糖，它让异步操作看起来像同步操作一样，使得代码更加易读。async/await 实际上就是对 Promise 的进一步封装，它使得异步操作更加简单明了。
  在 async 函数中，当遇到 await 关键字时，会暂停异步操作的执行，等待异步操作完成并返回结果，然后继续执行后面的代码。如果异步操作返回的是 Promise 对象，那么可以使用 await 关键字来等待 Promise 对象的状态变为 fulfilled 或 rejected。

  Promise 和 async/await 的区别：
  Promise 和 async/await 都是用于解决异步编程问题的机制，但是它们有一些不同之处。

  Promise 是一种基于回调函数的异步编程解决方案，它通过 then() 和 catch() 方法来处理异步操作的结果。Promise 的主要优点是可以避免回调函数的嵌套，使代码更加简洁易懂。但是在使用 Promise 时，需要手动管理 Promise 对象的状态，编写相应的回调函数，代码量可能会比较大。

  async/await 是基于 Promise 的语法糖，它让异步操作看起来像同步操作一样，使得代码更加易读。async/await 实际上就是对 Promise 的进一步封装，它使得异步操作更加简单明了。使用 async/await 可以直接获取异步操作的结果，并且不需要手动管理 Promise 对象的状态。

  应用场景：
  由于 Promise 和 async/await 都是用于解决异步编程问题的，因此它们的应用场景都与异步操作有关。

  Promise 的应用场景主要包括：

  处理多个异步操作的并发执行；
  处理多个异步操作的顺序执行；
  处理多个异步操作的错误处理。
  async/await 的应用场景主要包括：

  顺序执行多个异步操作，并且不需要处理并发执行；
  使用 try/catch 来捕获和处理异步操作的错误；
  通过 await 关键字来等待异步操作的完成。

  算法：
  1. 冒泡排序
  冒泡排序是一种简单的排序算法，基本思想是从头到尾比较相邻的两个元素，如果逆序则交换，直到整个序列有序。
  代码实现：
      function bubbleSort(arr) {
        const len = arr.length;
        for (let i = 0; i < len - 1; i++) {
          for (let j = 0; j < len - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
              [arr[j], arr[j + 1]] = [arr[j + 1], arr[j]];
            }
          }
        }
        return arr;
      }
  算法分析：
    时间复杂度：$O(n^2)$
    空间复杂度：$O(1)$
    稳定性：稳定排序
  
  2. 快速排序
  快速排序是一种高效的排序算法，基本思想是通过一趟排序将待排记录分割成独立的两部分，其中一部分记录的关键字均比另一部分关键字小，然后分别对这两部分记录继续进行排序，最终得到有序序列。

  代码实现：
      function quickSort(arr) {
        if (arr.length <= 1) {
          return arr;
        }
        const pivotIndex = Math.floor(arr.length / 2);
        const pivot = arr.splice(pivotIndex, 1)[0];
        const left = [];
        const right = [];
        for (let i = 0; i < arr.length; i++) {
          if (arr[i] < pivot) {
            left.push(arr[i]);
          } else {
            right.push(arr[i]);
          }
        }
        return [...quickSort(left), pivot, ...quickSort(right)];
      }
  算法分析：
  时间复杂度：最坏情况下为$O(n^2)$，平均情况下为$O(n\log n)$
  空间复杂度：最坏情况下为$O(n)$，平均情况下为$O(\log n)$
  稳定性：不稳定排序

  Vue
  1. 源码主要分为：编译器(compiler)，核心库(core)，以及运行时(runtime)
      编译器(compiler)：主要用于将模板(template)转换成渲染函数(render function)。模板是一段包含Vue指令的HTML代码，而渲染函数则是一个返回虚拟DOM(Virtual DOM)的JavaScript函数。

      核心库(core)：主要包含Vue.js的基本功能，包括响应式系统、虚拟DOM、组件等。

      运行时(runtime)：是将编译器(compiler)和核心库(core)合并后的版本，包含了所有Vue.js的功能，并且没有编译器。

  2. 以下是Vue.js源码的详细分析：
  ① 响应式系统
  Vue.js的响应式系统是其最重要的功能之一。当数据变化时，页面会自动更新。该系统基于ES5的Object.defineProperty()方法实现。Vue.js会为每个属性创建一个dep(dependency)实例，当属性发生变化时，会通知所有依赖于该属性的watcher实例更新。Watcher是响应式系统的核心。每个Watcher实例都会监听一个数据变化，当该数据变化时，它会触发一个回调函数。
  ② 虚拟DOM
  Vue.js的虚拟DOM是一个JavaScript对象，用于表示真实DOM的结构。Vue.js将模板转换为虚拟DOM，然后通过对比新旧虚拟DOM的差异，最终将变化更新到真实DOM中。Vue.js的虚拟DOM采用了diff算法优化性能。
  ③ 组件
  Vue.js中的组件是一种抽象概念，可以被定义为可复用的代码块。每个组件都有自己的状态和行为，并且可以接收外部数据。Vue.js通过将组件树转换为虚拟DOM来实现高效的渲染。
  ④ 模板编译
  Vue.js的模板编译器(compiler)可以将模板转换为渲染函数(render function)，从而提高性能。Vue.js的模板语法使用了类似于HTML的标记，但具有更强的表达能力。Vue.js的模板编译器使用了类似于正则表达式的算法来解析模板，从而生成渲染函数。
  总体来说，Vue.js的源码实现了一个高效的响应式系统，基于虚拟DOM实现了高效的渲染，同时提供了组件和模板编译等功能，可以用于构建复杂的Web应用程序。

  Proxy：
  ES6中的Proxy是一个非常强大的特性，它允许您拦截对对象的访问并对其进行处理。这意味着您可以在对象上设置一个代理，然后在任何时候都可以检测到对象属性的访问，并在属性被访问之前或之后执行自定义逻辑。Proxy允许您在运行时修改对象的行为。
  
  1. 属性拦截
      const target = {
        name: 'john',
        age: 30
      }
      const proxy = new Proxy(target, {
        get(target, property) {
          if(property === 'age') {
            throw new Error('Access denied!')
          } else  {
            return target[property]
          }
        }
      })
      console.log(proxy.name); // 'John'
      console.log(proxy.age); // Error: Access denied
  2. 函数调用拦截
  使用Proxy，您可以拦截对对象方法的调用。例如，您可以使用Proxy来记录每次调用方法的时间：
      const target = {
        hello() {
          console.log('Hello');
        }
      };

      const proxy = new Proxy(target, {
        apply(target, thisArg, argumentsList) {
          console.log(`Calling ${argumentsList[0]} at ${new Date()}`);
          return target.apply(thisArg, argumentsList);
        }
      });

      proxy.hello('world'); // Calling world at Tue Mar 09 2023 10:00:00 GMT+0800 (China Standard Time) // Hello

  3. 构造函数拦截
  使用Proxy，您可以拦截对类的构造函数的调用。例如，您可以使用Proxy来验证构造函数的参数：
      class Person {
        constructor(name) {
          this.name = name;
        }
      }

      const proxy = new Proxy(Person, {
        construct(target, argumentsList) {
          if (!argumentsList[0]) {
            throw new Error('Name is required');
          } else {
            return new target(...argumentsList);
          }
        }
      });

      const john = new proxy('John');
      const jane = new proxy(); // Error: Name is required
  总之，Proxy是一种强大的功能，可以用于许多用例。它允许您在运行时拦截并修改对象的行为，并且可以用于增强对象的安全性、验证和日志记录等。

    swtich：
      const arr = [1,2,3,4,5,6]
      const arrRandomIndex = Math.floor(Math.random() * arr.length)
      const target = arr[arrRandomIndex]
      switch (target) {
        case 1:
          console.log(1)
          break
        case 2:
          console.log(2)
          break
        case 3:
          console.log(3)
          break
        case 4:
          console.log(4)
          break
        case 5:
          console.log(5)
          break
        case 6:
          console.log(6)
          break
        default:
          console.log(target)
      }
  
  函数中的this
  1. 函数形式调用，this指向window
  2. 以方法的形式调用，this指向调用方法的对象
    function fn(){
      console.log(this)
      console.log('fn', this)
    }
    const obj = {
      name: '孙悟空'
    }
    obj.test = fn
    obj.test()
    const obj2 = {
      name: '猪八戒',
      test: fn
    }
    obj2.test()

  箭头函数 this
  1. 箭头函数没有自己的this,它的this由外层作用域决定
  2. 箭头函数的this和它的调用方式无关
  ([参数]) => 返回值

    () => 返回值
    a => 返回值
    (a,b) => 返回值

    function fn(){
      console.log('fn', this)
    }
    const fn2 = () => {
      console.log('fn2', this)
    }
    // fn() window
    // fn2() window

    const obj = {
      name: '孙悟空',
      fn,
      fn2,
      sayHello(){
        console.log(this.name)
        function t(){
          console.log('t', this)
        }
        t()
        const t2 = () => {
          console.log('t2', this)
        }
        t2()
      }
    }

  构造函数
    class Person {
      a = 1
      constructor(name, age, gender) {
        this.name = name
        this.age = age
        this.gender = gender
      }
    }
    const p1 = new Person("孙悟空", 16, '男')
    const p2 = new Person("猪八戒", 17, '男')
    const p3 = new Person("沙和尚", 18, '男')

    console.log('p1', p1)
    console.log('p2', p2)
    console.log('p3', p3)

  封装
  主要用来保证数据安全
  实现封装方式：
  1. 属性是优化 #
  2. 通过getter和setter方法来操作属性
    class Person{
      #name
      #age
      #gender
      constructor(name, age, gender) {
        this.#name = name
        this.#age = age
        this.#gender = gender
      }
      sayHello(){
        console.log(this.#name)
      }
      get gender(){
        return this.#gender
      }
      set gender(gender) {
        this.#gender = gender
      }
    }
    const p1 = new Person("孙悟空", 18, '男')
    p1.gender = '女' // call set gender
    console.log(p1.gender) // call get gender

  多态
  在JS中不会检查参数的类型，任何数据都可以作为参数传递
  要调用某个函数，无需指定类型，只要对象满足条件即可
  多态为我们提供了灵活性
    class Person {
      constructor(name) {
        this.name = name
      }
    }
    class Dog {
      constructor(name){
        this.name = name
      }
    }
    const person = new Person('Danny')
    const dog = new Dog('旺财')
    const sayHello = obj => {
      console.log(`Hello!,${obj.name}`)
    }
    sayHello(person)
    sayHello(dog)
  
  继承
  通过继承可以再不修改一个类的情况下对齐进行扩展
  OCP开闭原则：程序应该对修改关闭，对继承开放
  class Animals {
    constructor(name){
      this.name = name
    }
    sayHello(){
      console.log("动物在叫~")
    }
  }
  class Dog extends Animals{
    // 重写
    sayHello(){
      console.log('汪汪汪')
    }
  }
  class Cat extends Animals{
    // 重写构造函数
    consturctor(name){
      // 重写构造函数第一行必须先写super()
      super(name)
      this.age = age
    }
  }
  const dog = new Dog('旺财')
  const cat = new Cat('汤姆', 3)
  console.log(dog)
  dog.sayHello()

