## Redundancy
These samples are a collection of redundant or irrelevant code repetations which were really implemented in production as some point!

### Check them All!
The case was highlighting the current menu according to matched URL. The developer was very patient while coding, cause, every case were checked separately!


#### How it was?
```javascript
// [left menu item selected]
var pageLink = location.href;
if (pageLink.indexOf("kredi-notu") != "-1") {
	$('#kredi-notu').addClass('active');
} else if (pageLink.indexOf("risk-raporu") != "-1") {
	$('#risk-raporu').addClass('active');
} else if (pageLink.indexOf("uyari-hizmeti") != "-1") {
	$('#uyari-hizmeti').addClass('active');
} else if (pageLink.indexOf("izleme") != "-1") {
	$('#izleme').addClass('active');
} else if (pageLink.indexOf("not-danismanim") != "-1") {
	$('#not-danismanim').addClass('active');
} else if (pageLink.indexOf("takipci") != "-1") {
	$('#kimligim-guvende').addClass('active');
} else if (pageLink.indexOf("nedir") != "-1") {
	$('#nedir').addClass('active');
} else if (pageLink.indexOf("kredi-kayit-burosu") != "-1") {
	$('#kredi-kayit-burosu').addClass('active');
} else if (pageLink.indexOf("basin-odasi") != "-1") {
	$('#basin-odasi').addClass('active');
} else if (pageLink.indexOf("videolar") != "-1") {
	$('#videolar').addClass('active');
} else if (pageLink.indexOf("cek-raporu") != "-1") {
	$('#cek-raporu').addClass('active');
} else if (pageLink.indexOf("cek-endeksi") != "-1") {
	$('#cek-endeksi').addClass('active');
} else if (pageLink.indexOf("diger-kisi-raporlari") != "-1") {
	$('#3-kisi-raporlari').addClass('active');
}
```

#### How it should be?

```javascript
// according to website, URLs end with '/'
var url = location.href.split('/'),
	slug = url[url.length-2];

/* Did not check the system, they could use ajax for page loading.
   Better removing active class just in case.
   Also in batch-removeClass situations like this, consider removing
   className only from the elements that have that className.
   Use .find('li.active') instead of .find('li')
*/
$(".leftMenu").find('li.active')
    .removeClass('active')
    .filter("#" + slug)
    .addClass('active');
```

In the first case, for each new menu item, you have to add an `else` block. Also come on, why you should repeating these much code, please please please, __be smart while coding__...
