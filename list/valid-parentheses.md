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