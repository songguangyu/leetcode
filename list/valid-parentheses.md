## leedcode地址
https://leetcode.com/problems/valid-parentheses/description

## 解题方案
```
/**
 * @param {string} str
 * @return {boolean}
 */
var isValid = function (str) {
 const stack = [];
 const mapper = new Map([
  ["(", ")"],
  ["{", "}"],
  ["[", "]"]
 ]);

 for(let i = 0; i< str.length; i++) {
     if(mapper.has(str[i])) {
      stack.push(str[i])
     } else {
      const peak = stack.pop();
      if (str[i] === mapper.get(peak)) {
          continue;
      }
      return false;
     }
 }
 if (stack.length !== 0) { return false }
 return true;
}

```

var isValid = function (str) {
  const preTag = /<\s?[a-z]+\s?(>|/>)/;
  const stack = [];
  const tempIndex = 0;
  for(let i = 0; i < str.length; i++) {
    if(str[i] === '<') {
      tempIndex = i;
    }
    if ( str[i] === '>') {
      const tag = str.slice(tempIndex, i);
    }
    if (str[i]+str[i+1] === '/>') {

    }
  }
}

## 深入思考，判断HTML元素标签是否闭合？
case 1: <input />
case 2: <div></div>
case 3: <span><123</span>
case 3: <span>123></span>
case 4: <span><123></span>
case 5: <span><sgy/></span>