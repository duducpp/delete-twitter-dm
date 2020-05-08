# Automate deleting twitter direct messages

This is a simple script that uses jquery to automatizate the process to delete old DMS from twitter

# How to use
Go to your DMs page and paste it on console
```JS
let jquery = $;
function sleep(ms) {
	return new Promise((resolve) => setTimeout(resolve, ms));
}
async function deleteDmsByYear(Year) {
	while (true) {
		let dm = jquery(`time[datetime*='${Year}-']`);

		if (!dm) break;

		dm.click();
		await sleep(500);

		jquery("a[href*='/info']").click();
		await sleep(500);

		jquery(
			'div[class="css-18t94o4 css-1dbjc4n r-1777fci r-1jayybb r-1j3t67a r-9qu9m4 r-o7ynqc r-6416eg"]'
		).click();
		await sleep(500);

		jquery(
			'div[class="css-901oao r-1awozwy r-jwli3a r-6koalj r-18u37iz r-16y2uox r-1qd0xha r-a023e6 r-vw2c0b r-1777fci r-eljoum r-dnmrzs r-bcqeeo r-q4m81j r-qvutc0"]'
		).click();
		await sleep(500);
	}
}
```

Then run this with the year that you are willing to delete
```JS
deleteDmsByYear('2019');
```
