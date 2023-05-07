```javascript
const simplifiedArray = (arr) => {
	const isPrime = (n) =>
		n > 1 &&
		Array.from({ length: Math.floor(Math.sqrt(n)) - 1 }, (_, i) => i + 2).every(
			(x) => n % x
		);
	const simplify = (arr) =>
		arr.reduce(
			(acc, val, i, arr) =>
				i === 0 || isPrime(val) !== isPrime(arr[i - 1])
					? [...acc, val]
					: [...acc.slice(0, -1), acc[acc.length - 1] + val],
			[]
		);
	while (true) {
		const simplified = simplify(arr);
		if (JSON.stringify(simplified) === JSON.stringify(arr)) {
			return simplified;
		} else {
			arr = simplified;
		}
	}
};
```
