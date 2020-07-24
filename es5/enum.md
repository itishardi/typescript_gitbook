# enum

enum 枚举类型

```text
enum Gender{
    Boy,
    Girl,
    Unknown
}
let userSex: Gender = Gender.Boy;
console.dir(Gender);
```

上述enum由es3实现

```text
var Gender;
(function (Gender) {
    Gender[Gender["Boy"] = 0] = "Boy";
    Gender[Gender["Girl"] = 1] = "Girl";
    Gender[Gender["Unknown"] = 2] = "Unknown";
})(Gender || (Gender = {}));
var userSex = Gender.Boy;
console.dir(Gender);
```

重点：Gender\["Boy"\] = 0的返回值是0，用于参数值给Gender\[0\]的赋值。

上述ES3实现的enum在浏览器内的本质：

```text
typeof(Gender)
"object"

Object.keys(Gender)
["0", "1", "2", "Boy", "Girl", "Unknown"]

Object.values(Gender)
["Boy", "Girl", "Unknown", 0, 1, 2]

console.dir(Gender)
(Object)
    0: "Boy"
    1: "Girl"
    2: "Unknown"
    Boy: 0
    Girl: 1
    Unknown: 2
    length: 6
    __proto__: Array(0)
```



