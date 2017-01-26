# Evolved Tools
External library to provide useful tools currently missing in JavaScript. Compatible with jQuery, AngularJS and other libraries and frameworks.

Note: _this is a collection of functionalities and tools that I found useful, please contact me if you would like to add more._

Note 2: _I suggest to delete any main section you don't need in your project to make the library smaller, this is why I did not minify it_



- [Basic functionalities](#basic-functionalities)
    - [$$et.die(data)](#die)
    - [$$et.isset(variable)](#isset)
    - [$$et.empty(variable)](#empty)
    - [$$et.is_bool(variable)](#is_bool)
    - [$$et.is_numeric(variable)](#is_numeric)
    - [$$et.is_string(variable)](#is_string)
    - [$$et.is_array(variable)](#is_array)
    - [$$et.is_object(variable)](#is_object)
    - [$$et.is_file(variable)](#is_file)
    - [$$et.is_blob(variable)](#is_blob)
    - [$$et.is_function(variable)](#is_function)
    - [$$et.is_FileReader(variable)](#is_FileReader)
    - [$$et.is_email(variable)](#is_email)
    - [$$et.getType(variable)](#getType)
    - [$$et.getBool(flag)](#getBool)
    - [$$et.getInt(number)](#getInt)
    - [$$et.getFloat(number)](#getFloat)
    - [$$et.cloneObject(source)](#cloneObject)
    - [$$et.mergeObjects(mainObject, poolObject)](#mergeObjects)
    - [$$et.getObjectLength(source)](#getObjectLength)
- [Strings tools](#strings-tools)
    - [Documentation in progress...](#in_progress)
- [Files tools](#files-tools)
- [Images tools](#images-tools)
- [Videos tools](#videos-tools)
- [Operative System information](#os-info)
- [Browser information](#browser-info)



### <a name="basic-functionalities"></a>Basic functionalities:

Truncate the execution of the current script and print the "data" variable in the logs

<a name="die"></a>
`$$et.die(data)`

> Example:

```
/*
 * This will print "b" then a forced "Uncaught Error"
 * will stop the execution of your script
 */
var foo = ['a', 'b', 'c'];

for (var i=0; i<foo.length; i++) {
    if (i == 1) $$et.die(foo[i]);
}
```

---

Check if a variable has been created and defined

<a name="isset"></a>
`$$et.isset(variable)`

> Example:

```
var foo;
var name = 'Jack';

console.log($$et.isset(foo)); // false
console.log($$et.isset(name)); // true
```

---

Check if a variable is isset but empty

It is similar to "isset", but it also checks: Booleans, Strings, Numbers, Arrays, Objects

<a name="empty"></a>
`$$et.empty(variable)`

> Example:

```
var notset;
var foo = '';
var number = 2;
var name = 'Jack';
var nolist = new Array();
var list = ['a', 'b', 'c'];

console.log($$et.empty(notset)); // true
console.log($$et.empty(foo)); // true
console.log($$et.empty(number)); // false
console.log($$et.empty(name)); // false
console.log($$et.empty(nolist)); // true
console.log($$et.empty(list)); // false
```

---

Check if a variable is a "Boolean"

<a name="is_bool"></a>
`$$et.is_bool(variable)`

> Example:

```
var name = 'Jack';
var visible = false;

console.log($$et.is_bool(name)); // false
console.log($$et.is_bool(visible)); // true
```

---

Check if a variable is a "Number"

<a name="is_numeric"></a>
`$$et.is_numeric(variable)`

> Example:

```
var name = 'Jack';
var height = 17.5;
var age = 32;

console.log($$et.is_numeric(name)); // false
console.log($$et.is_numeric(height)); // true
console.log($$et.is_numeric(age)); // true
```

---

Check if a variable is a "String"

<a name="is_string"></a>
`$$et.is_string(variable)`

> Example:

```
var name = 'Jack';
var height = "17.5"; // Note the quotation marks
var age = 32;

console.log($$et.is_string(name)); // true
console.log($$et.is_string(height)); // true
console.log($$et.is_string(age)); // false
```

---

Check if a variable is an "Array"

<a name="is_array"></a>
`$$et.is_array(variable)`

> Example:

```
var name = 'Jack';
var foo = []; // or new Array()
var list = ['a', 'b', 'c'];

console.log($$et.is_array(name)); // false
console.log($$et.is_array(foo)); // true
console.log($$et.is_array(list)); // true
```

---

Check if a variable is an "Object"

<a name="is_object"></a>
`$$et.is_object(variable)`

> Example:

```
var name = 'Jack';
var foo = {}; // or new Object()
var list = { a : 'a', b : 'b', c : 'c' };

console.log($$et.is_object(name)); // false
console.log($$et.is_object(foo)); // true
console.log($$et.is_object(list)); // true
```

---

Check if a variable is a "File"

<a name="is_file"></a>
`$$et.is_file(variable)`

> Example:

```
var name = 'Jack';
var f = new File([""], "filename");

console.log($$et.is_file(name)); // false
console.log($$et.is_file(f)); // true
```

---

Check if a variable is a "Blob"

<a name="is_blob"></a>
`$$et.is_blob(variable)`

> Example:

```
var name = 'Jack';
var b = new Blob();

console.log($$et.is_blob(name)); // false
console.log($$et.is_blob(b)); // true
```

---

Check if a variable is a "Function"

<a name="is_function"></a>
`$$et.is_function(variable)`

> Example:

```
var name = 'Jack';
function f() {};
var lambda_f = function() {};

console.log($$et.is_function(name)); // false
console.log($$et.is_function(f)); // true
console.log($$et.is_function(lambda_f)); // true
```

---

Check if a variable is a "FileReader"

<a name="is_FileReader"></a>
`$$et.is_FileReader(variable)`

> Example:

```
var name = 'Jack';
var file = new FileReader();

console.log($$et.is_FileReader(name)); // false
console.log($$et.is_FileReader(file)); // true
```

---

Check if a variable is a "Email"

<a name="is_email"></a>
`$$et.is_email(variable)`

> Example:

```
var name = 'Jack';
var email = 'crocefabiopa@gmail.com';

console.log($$et.is_email(name)); // false
console.log($$et.is_email(email)); // true
```

---

Returns the type of a variable

<a name="getType"></a>
`$$et.getType(variable)`

> Example:

```
var variable = new Blob();

console.log($$et.getType(variable)); // [object Blob]
```

---

Returns a boolean value from a variable

<a name="getBool"></a>
`$$et.getBool(variable)`

> Example:

```
var variable = 'true';
var name = 'Jack';
var foo = 1;
var boolean = true;
var another_boolean = false;

console.log($$et.getBool(variable)); // true
console.log($$et.getBool(name)); // false
console.log($$et.getBool(foo)); // true
console.log($$et.getBool(boolean)); // true
console.log($$et.getBool(another_boolean)); // false
```

---

Returns an integer value from a variable

<a name="getInt"></a>
`$$et.getInt(variable)`

> Example:

```
var variable = '32';
var foo = 42;
var question = 'height 12';
var from_string = '42 is the answer to the ultimate question of life the universe and everything';
var test = 14.5;
var boolean = true;

console.log($$et.getInt(variable)); // 32
console.log($$et.getInt(foo)); // 42
console.log($$et.getInt(question)); // NaN
console.log($$et.getInt(from_string)); // 42
console.log($$et.getInt(test)); // 14
console.log($$et.getInt(boolean)); // 1
```

---

Returns a float value from a variable

<a name="getFloat"></a>
`$$et.getFloat(variable)`

> Example:

```
var variable = '32.3';
var foo = 42.05;
var question = 'height 12.7';
var from_string = '12.7 is the height';
var test = 14;
var boolean = true;

console.log($$et.getFloat(variable)); // 32.3
console.log($$et.getFloat(foo)); // 42.05
console.log($$et.getFloat(question)); // NaN
console.log($$et.getFloat(from_string)); // 12.7
console.log($$et.getFloat(test)); // 14
console.log($$et.getFloat(boolean)); // 1
```

---

Clones an object into another

<a name="cloneObject"></a>
`$$et.cloneObject(variable)`

> Example:

```
var variable = new Object();
var foo = variable;
var another_obj = $$et.cloneObject(variable);

console.log(variable === foo); // true
console.log(variable === another_obj); // false
```

---

Merges two objects (the one on the right has priority)

<a name="mergeObjects"></a>
`$$et.mergeObjects(variable)`

> Example:

```
var obj_1 = { a : 'a', b : 'b' };
var obj_2 = { c : 'c', d : 'd', e : 'e' };
var priority = { f : 'f', a : 'ops' };

console.log($$et.mergeObjects(obj_1, obj_2)); // Object {a: "a", b: "b", c: "c", d: "d", e: "e"}
console.log($$et.mergeObjects(obj_1, priority)); // Object {a: "ops", b: "b", c: "c", d: "d", e: "e", f: "f"}
// Note how the second console.log shows a list of all 3 objects
// because obj_1 was already merged with obj_2
```

---

Get the number of keys of an object

<a name="getObjectLength"></a>
`$$et.getObjectLength(variable)`

> Example:

```
var obj = { a : 'a', b : 'b' };

console.log($$et.getObjectLength(obj)); // 2
```

---


### <a name="strings-tools"></a>Strings tools:

<a name="in_progress"></a>
_Documentation in progress..._

TODO


### <a name="files-tools"></a>Files tools:

TODO


### <a name="images-tools"></a>Images tools:

TODO


### <a name="videos-tools"></a>Videos tools:

TODO


### <a name="os-info"></a>Operative System information:

TODO


### <a name="browser-info"></a>Browser information:

TODO
