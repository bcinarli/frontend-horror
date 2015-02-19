# Selectors
These samples are a collection of selector mistakes which were really implemented in production as some point!

## They Say `ID` Selector has the best performance
The case was in a list of select items that SelectBox plugin applied. Developer obviously thought, selecting jQuery element with `id` selector will have better performance, according to articles in various places.

#### How was it?
```javascript
$(function(){
	$("#combobox1").selectbox();
    $("#combobox2").selectbox();
    $("#combobox3").selectbox();
    $("#combobox4").selectbox();
    $("#combobox5").selectbox();
    $("#combobox6").selectbox();
    $("#combobox7").selectbox();
    $("#combobox8").selectbox();
    $("#combobox9").selectbox();
    $("#combobox10").selectbox();
    $("#combobox11").selectbox();
    $("#combobox12").selectbox();
    $("#combobox13").selectbox();
    $("#combobox14").selectbox();
    $("#combobox15").selectbox();
    $("#combobox16").selectbox();
    $("#combobox17").selectbox();
    $("#combobox18").selectbox();
    $("#combobox19").selectbox();
    $("#combobox20").selectbox();
    $("#combobox21").selectbox();
    $("#combobox22").selectbox();
    $("#combobox23").selectbox();
    $("#combobox24").selectbox();
    $("#combobox25").selectbox();
    $("#combobox26").selectbox();
    $("#combobox27").selectbox();
});
```

#### How it should be?
```javascript
$(function(){
	$(".selectbox").selectbox();
});
```
In older browsers for ID selector, jQuery uses the native `document.getElementById` method, and a regex for class selector. However, in this case, by selecting elements with class will be faster since with class selector, you get the collection at once, not one by one.