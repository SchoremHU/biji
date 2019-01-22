Array/forEach/Function/join/concat/map/filter/reduce/sort
-----------------------------------------------------------------------
NAN '' 0 undefined unll</br>
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
a = [1,2,3,4,5]</br>
a.forEach( function(x,y){ console.log(x,y) } )</br>
//</br>
 1 0</br>
 2 1</br>
 3 2</br>
 4 3</br>
 5 4</br>
//</br>
可以理解为下面函数</br>
function f(fn){ console.log('接收到一个函数') return undefined }</br>
f(  function(){} ) //'接收到一个函数'</br>

-----------------------------------------------------------------------
map 功能与forEach差不多，区别是有返回值，并储存起来</br>
a.map(function(value, key){ return value * 2 })</br>
等同于下面</br>
a.map( value => value * 2 )</br>

-----------------------------------------------------------------------
filter  过滤的意思   用法跟 map forEach 相同</br>
a = [1,2,3,4,5,6,7,8,9]</br>
a.flilter(function(value,key){ return value >=5 }) //[5,6,7,8,9]</br>

-----------------------------------------------------------------------

a.filter 与 a.map 连用 </br>
先过滤之后进行运算并返回值</br>

-----------------------------------------------------------------------
reduce  遍历数组，</br>
a = [1,2,3,4,5,6]</br>
a.reduce(function(sum,x){ return sum + x }) // 21</br>
</br>
sum 初始值是 1 ，x 是 value</br>
运算sum + x 之后赋值给 sum ，再进行sum + x ，知道运算结束。</br>
</br>
map 可以用 reduce 表示</br>
a = [1,2,3]</br>
a.reduce(function(arr,n){ arr.push(n*2); return arr },[]) //[2,4,6]</br>

filter 用 reduce 表示</br>
a = [1,2,3,4,5,6,7,8,9]</br>
a.reduce(function(arr,n){ if(n%2==0){ arr.push(n) };return arr  },[]) //[2,4,6,8,10]</br>

-----------------------------------------------------------------------
sort  数组排序 添加函数，函数返回值的真假判断排序次序</br>
a = [5,8,1,3,6,7,9]</br>
a.sort() // [1,3,5,6,7,8,9]</br>
a.sort( function(x,y){return x-y} ) //[1,3,5,6,7,8,9]</br>
a.sort( function(x,y){return y-x} ) //[9,8,7,6,5,3,1]</br>

-----------------------------------------------------------------------
join 插入</br>
a = [1,2,3]</br>
a.join('正') //"1正2正3"</br>
数组变字符串的方法 </br>
a.join() //"1,2,3"     括号内空白，默认是加逗号  , </br>

-----------------------------------------------------------------------
concat   把两个链接起来</br>
a = [1,2,3]</br>
b = [4,5,6]</br>
a.concat(b) //[1,2,3,4,5,6]</br>

concat 会返回一个新的数组 ，与赋值不同</br>
var a =[1,2,3]</br>
var b = a.concat([])</br>
b  //[1,2,3]</br>
a === b  //false</br>


-----------------------------------------------------------------------
Function 是全局对象 function 是关键字</br>
var a = new  Function( 'a','b','return a + b')</br>
括号中第一个字符串表示传入第一个参数，第二个字符串表示第二个传入参数，第三个....，最后一个为函数体。</br>
等同于下面</br>
var a = function( a,b ){ return a + b ; }</br>

匿名函数  function （）{}</br>
var f = function (){}</br>