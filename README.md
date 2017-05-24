# stackoverflow 前端热门问题汇总

#### 1. 如何使用 JavaScript 重定向到另一个界面？

>[How to redirect to another webpage in JavaScript/jQuery?](https://stackoverflow.com/questions/503093/how-to-redirect-to-another-webpage-in-javascript-jquery)
> StackOverflow

**如果模拟用户点击事件行为，请使用  `location.href`** 
**如果要模拟HTTP重定向，请使用 `location.replace`** 

```
location.href='http://www.gm-medicare.com';
location.replace('http://www.gm-medicare.com');
```

#### 2. JavaScript 如何判断字符串是否包含某些字符？

>[How to check whether a string contains a substring in JavaScript?](https://stackoverflow.com/questions/1789945/how-to-check-whether-a-string-contains-a-substring-in-javascript)
>StackOverflow

**1. indexOf方法**`推荐` 
```
//indexOf() 方法可返回某个指定的字符串值在字符串中首次出现的位置。
//如果没有找到匹配的字符串则返回 -1。
var str = 'hello',
	subStr = 'he';
str.indexOf( subStr ) !== -1 ;
```
**2. ECMAScript 6 includes方法**`有兼容性风险` 
```
var string = 'gmmedicare',
    substring = 'gm';
string.includes(substring);
```
**3. search方法** 
```
var string = 'gmmedicare',
    expr = '/medicare/';
string.search(expr);
```
**4. lodashJS includes**`需要引入lodash.js库`
```
var string = "'foo',
    substring = 'oo';
_.includes(string, substring);
```
**5. RegExp**
```
var string = 'foo',
    expr = /oo/;  
expr.test(string);
```
**6. Match**
```
var string = 'foo',
    expr = '/oo/';
string.match(expr);
```
#### 3. jQuery 如何判断元素是否隐藏？

> [How do I check if an element is hidden in jQuery?](https://stackoverflow.com/questions/178325/how-do-i-check-if-an-element-is-hidden-in-jquery)
> StackOverflow

**1.  jQuery is方法**`推荐`
```
$('#js-id').is(':hidden');
```
**2.  jQuery 选择器**
```
$('#js-id:hidden');
```
#### 4. function 声明 VS function 表达式？

> [var functionName = function() {} vs function functionName() {}](https://stackoverflow.com/questions/336859/var-functionname-function-vs-function-functionname)
> StackOverflow

#### 5. JavaScript 使用相等符号==还是进行比较？

> [Which equals operator (== vs ===) should be used in JavaScript comparisons?](https://stackoverflow.com/questions/359494/which-equals-operator-vs-should-be-used-in-javascript-comparisons)
> StackOverflow

#### 6. JavaScript 如何使字符串首字母大写？

**1. js 实现**

```
// 注意这里没有检查 str 是否字符串类型
function capitalizeFirstLetter (str) {
	return str.charAt(0).toUpperCase() + str.slice(1);
}
```
**2. css 实现**

```
p:first-letter{
	text-transform:capitalize;
}
```

#### 7. JavaScript 如何替换重复的字符？

> [How to replace all occurrences of a string in JavaScript?](https://stackoverflow.com/questions/1144783/how-to-replace-all-occurrences-of-a-string-in-javascript)
> StackOverflow

1. 正则表达式

```
function replaceAll(str, search,  replacement) {
	return str.replace( new RegExp(search, g), replacement); 
}
```
2. split 和 jion 
```
function replaceAll(str, search, replacement) {
	return str.split(search).join(replacement); 
}
```
#### 8. 如何异步上传文件？

> [How can I upload files asynchronously?](https://stackoverflow.com/questions/166221/how-can-i-upload-files-asynchronously)
> StackOverflow

#### 9. 如何循环或枚举 JavaScript 对象？

> [How do I loop through or enumerate a JavaScript object?](https://stackoverflow.com/questions/684672/how-do-i-loop-through-or-enumerate-a-javascript-object)
> StackOverflow

**1.for in**`强制使用hasOwnProperty方法过滤来自原型对应的属性和方法，否则会带来性能问题`
```
var key,
    obj = {
	firstName: 'li',
	lastName: 'longlong',
	showName: function () {
		console.log( this.firstName + this.last.name );
	}	
};
for( key in obj ) {
	if( obj.hasOwnProperty(key) ) {
		console.log( key + ': ' + obj[key] );
	}
}
```
#### 10. 检测JavaScript对象的属性是否 undefined 的最佳实现方式？

> [Detecting an undefined object property](https://stackoverflow.com/questions/27509/detecting-an-undefined-object-property)
> StackOverflow


**1.typeof**

```
'undefined' === typeof variable;
// or 
'undefined' === typeof obj.prop;
```
#### 11. JavaScript 如何清空数组？

> [How do I empty an array in JavaScript?](https://stackoverflow.com/questions/1232040/how-do-i-empty-an-array-in-javascript?rq=1)
>stackoverflow

**1. 重新赋值**`小心指针引用问题`
```
var arr = [1, 2, 3, 4];
arr2 = arr;
arr=[];
console.log(arr); --> []
console.log(arr2); --> [1, 2, 3, 4]
```
**2.设置数组长度**
```
var arr = [1, 2, 3, 4];
arr2 = arr;
arr.length=0;
console.log(arr); --> []
console.log(arr2); --> []
```
**3. splice**
```
var arr = [1, 2, 3, 4];
arr2 = arr;
arr.splice(0, arr.length);
console.log(arr); --> []
console.log(arr2); --> []
```
**4. while 循环**
```
var arr = [1, 2, 3, 4];
arr2 = arr;
while(.length > 0) {
    arr.pop();
}
console.log(arr);
console.log(arr2);
```
####  12. 如何在数组的指定位置中插入一个新的值？

> [How to insert an item into an array at a specific index?](https://stackoverflow.com/questions/586182/how-to-insert-an-item-into-an-array-at-a-specific-index)
> StackOverflow

**1. splice**
```
var arr = [];
arr[0]  = 'Jani';
arr[1]  = 'Hege';
arr[2]  = 'Stale';
arr[3]  = 'Kai Jim';
arr[4]  = 'Borge';
console.log( arr.join() );
arr.splice( 2, 0, 'Lene') ;
console.log( arr.join() );
```
####  13. 如何查看JavaScript  对象的长度？

> [Length of a JavaScript object](https://stackoverflow.com/questions/5223/length-of-a-javascript-object)
> StackOverflow

**1. Object**
```
var myObject = new Object();
myObject["firstname"] = "Gareth";
myObject["lastname"] = "Simpson";
myObject["age"] = 21;
// 在 Object 上做方法扩展
Object.size = function ( obj ){
	var result = 0,
		key;
	for (key in obj) {
		if(obj.hasOwnProperty(key)) {
			result++;
		}
	 }
	 return result;
};
console.log( Object.size(myObject) )；
```
