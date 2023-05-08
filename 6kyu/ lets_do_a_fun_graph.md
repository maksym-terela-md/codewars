```javascript
const graph = (arr) => {
	const highest = Math.max(...arr);

	const rows = [];
	for (let j = highest; j >= 0; j--) {
		const row = [];
		for (const item of arr) {
			if (item < j) row.push("......");
			else if (item === j) row.push(" ____ ");
			else row.push("|    |");
		}

		const axis = (j === highest ? " ^ " : " | ") + j;
		row.push(axis);
		rows.push(row);
	}

	return rows.map((row) => row.join("")).join("\n");
};
```
