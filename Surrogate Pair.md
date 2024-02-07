[Unicode代理对（utf-16）](https://xinyuehtx.github.io/post/Unicode%E4%BB%A3%E7%90%86%E5%AF%B9.html)

代理项
```js
const strings = [
  // 单独的前导代理
  "ab\uD800",
  "ab\uD800c",
  // 单独的后尾代理
  "\uDFFFab",
  "c\uDFFFab",
  // 格式正确
  "abc",
  "ab\uD83D\uDE04c",
];

for (const str of strings) {
  console.log(str.isWellFormed());
}
// 输出：
// false
// false
// false
// false
// true
// true

```