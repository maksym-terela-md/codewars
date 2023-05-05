```javascript
const isConsecutive = (str) => {
  const matches = str.match(/(.)\1*/g) || [];
  const uniqueChars = new Set(matches.map((match) => match[0]));
  return matches.length === uniqueChars.size;
};
```
