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
