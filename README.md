# FE-Interview-Guide
2023前端面试、2023前端面试指南、前端面试、前端面试指南

1. Javascript

  ① 数据类型：原始数据类型 & 引用数据类型
  原始数据类型：number string boolean symbol null undefined
  引用数据类型：对象 数组 函数

  函数：
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





