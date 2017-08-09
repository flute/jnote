# javascript-变量对象



// demo2
function test() {
    console.log(foo);
    console.log(bar);

    var foo = 'Hello';
    console.log(foo);
    var bar = function () {
        return 'world';
    }

    function foo() {
        return 'hello';
    }
}

test();

function test() {
    function(){
        return 'world';
    }//假设堆地址x0fa0122
    
    function foo(){
        return 'hello';
    }
    var bar;

    console.log( foo );
    console.log( bar );
    var foo;
    foo = 'Hello';
    console.log(foo);
    bar = x0fa0122;
    
}
hello
undefined
Hello

当代码执行时会创建执行上下文，而执行上下文的生命周期分为创建阶段和执行阶段：
* 在执行上下文的创建阶段，执行上下文会创建变量对象、建立作用域链、确定this的指向
* 在代码执行阶段，完成的操作是变量赋值、函数引用及运行其他代码

变量对象的创建又分为三个步骤
1. 创建arguments对象
2. 检查当前执行上下文中的function函数声明，在变量对象中建立以该函数名命名的属性，属性的值为指向该函数在堆内存中的地址，如果该属性名已经存在，那么会被新的属性覆盖
3. 检查当前执行上下文中的变量声明，在变量对象中建立该属性并赋值为undefined，如果属性名已经存在，为防止同名的函数被覆盖，会直接跳过。



