```javascript
function midtownNav(start, end) {
	const parseAddress = (address) => {
		const [avenue, street] = address.split(" and ");
		const avenueNum = parseInt(avenue.match(/\d+/)[0]);
		const streetNum = parseInt(street.match(/\d+/)[0]);
		const streetPrefix = street.match(/E|W/)[0];
		return { avenueNum, streetNum, streetPrefix };
	};

	const {
		avenueNum: startAvenue,
		streetNum: startStreet,
		streetPrefix: startPrefix,
	} = parseAddress(start);
	const {
		avenueNum: endAvenue,
		streetNum: endStreet,
		streetPrefix: endPrefix,
	} = parseAddress(end);

	const eastWestBlocks = Math.abs(startAvenue - endAvenue);
	const northSouthBlocks = Math.abs(startStreet - endStreet);

	const eastWestDirection = startAvenue > endAvenue ? "east" : "west";
	const northSouthDirection = startStreet > endStreet ? "south" : "north";

	return `Walk ${northSouthBlocks} blocks ${northSouthDirection}, and ${eastWestBlocks} blocks ${eastWestDirection}`;
}
```
