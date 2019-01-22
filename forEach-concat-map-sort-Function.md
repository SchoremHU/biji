Array/forEach/Function/join/concat/map/filter/reduce/sort
-----------------------------------------------------------------------
NAN '' 0 undefined unll
string number boolean symbol object undefined null

-----------------------------------------------------------------------
Array </br>
var a = new Array(3) //a[] empty x3,length:3 </br>
Array 带一个参数，表示定义数组的length，a.length = 3,内容为空。</br>
var a = new Array(3,3) //a[3,3]</br>
表示数组 a [3,3]</br>

Array数组</br>
是一组按次序排列的一组值。</br>
数组是__proto__链不同的对象。</br>


伪数组</br>
原型链中没有Array.prototype</br>
arguments</br>

-----------------------------------------------------------------------
forEach   需要接收函数，函数必须接受两个参数,第一个参数x是数组a中的value ，第二个参数y是数组a中的key  ,没有返回值。</br>
a = [1,2,3,4,5]
a.forEach( function(x,y){ console.log(x,y) } )
//
     1 0
     2 1
     3 2
     4 3
     5 4
//
可以理解为下面函数
function f(fn){ console.log('接收到一个函数') return undefined }
f(  function(){} ) //'接收到一个函数'

-----------------------------------------------------------------------
map 功能与forEach差不多，区别是有返回值，并储存起来
a.map(function(value, key){ return value * 2 })
等同于下面
a.map( value => value * 2 )

-----------------------------------------------------------------------
filter  过滤的意思   用法跟 map forEach 相同
a = [1,2,3,4,5,6,7,8,9]
a.flilter(function(value,key){ return value >=5 }) //[5,6,7,8,9]

-----------------------------------------------------------------------

a.filter 与 a.map 连用 
先过滤之后进行运算并返回值

-----------------------------------------------------------------------
reduce  遍历数组，
a = [1,2,3,4,5,6]
a.reduce(function(sum,x){ return sum + x }) // 21

sum 初始值是 1 ，x 是 value
运算sum + x 之后赋值给 sum ，再进行sum + x ，知道运算结束。

map 可以用 reduce 表示
a = [1,2,3]
a.reduce(function(arr,n){ arr.push(n*2); return arr },[]) //[2,4,6]

filter 用 reduce 表示
a = [1,2,3,4,5,6,7,8,9]
a.reduce(function(arr,n){ if(n%2==0){ arr.push(n) };return arr  },[]) //[2,4,6,8,10]

-----------------------------------------------------------------------
sort  数组排序 添加函数，函数返回值的真假判断排序次序
a = [5,8,1,3,6,7,9]
a.sort() // [1,3,5,6,7,8,9]
a.sort( function(x,y){return x-y} ) //[1,3,5,6,7,8,9]
a.sort( function(x,y){return y-x} ) //[9,8,7,6,5,3,1]

-----------------------------------------------------------------------
join 插入
a = [1,2,3]
a.join('正') //"1正2正3"
数组变字符串的方法 
a.join() //"1,2,3"     括号内空白，默认是加逗号  , 

-----------------------------------------------------------------------
concat   把两个链接起来
a = [1,2,3]
b = [4,5,6]
a.concat(b) //[1,2,3,4,5,6]

concat 会返回一个新的数组 ，与赋值不同
var a =[1,2,3]
var b = a.concat([])
b  //[1,2,3]
a === b  //false


-----------------------------------------------------------------------
Function 是全局对象 function 是关键字
var a = new  Function( 'a','b','return a + b')
括号中第一个字符串表示传入第一个参数，第二个字符串表示第二个传入参数，第三个....，最后一个为函数体。
等同于下面
var a = function( a,b ){ return a + b ; }

匿名函数  function （）{}
var f = function (){}