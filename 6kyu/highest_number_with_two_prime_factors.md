```javascript
const highestBiPrimeFac = (p1, p2, nMax) => {
	let maxNumber = 0,
		k1Max = 0,
		k2Max = 0;

	for (let k1 = 1; p1 ** k1 <= nMax; k1++) {
		for (let k2 = 1; p1 ** k1 * p2 ** k2 <= nMax; k2++) {
			const num = p1 ** k1 * p2 ** k2;
			if (num > maxNumber) [maxNumber, k1Max, k2Max] = [num, k1, k2];
		}
	}

	return [maxNumber, k1Max, k2Max];
};
```
