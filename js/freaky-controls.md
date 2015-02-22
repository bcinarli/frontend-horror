# Freaky Controls
These samples are a collection of extremely wrong-way implemented controls which were really used in production as some point!

## If it is `false` then it is `true`!
The case was, allowing only numeric values in an input. The function checks the value, then returns __false__ _if the value is numeric_ (O.o)

### How was it?
```javascript
function OnlyNumericForText(obj, e) {
    var k;
    k = (e.which) ? e.which : e.keyCode;
    if (k >= 48 && k <= 57)
        return false;
    else
        return true;
}

$(".numeric").on('keypress', function (event) {
	return !OnlyNumericForText(this, event);
});
```

### How could it be, plausible better solution(s)? 
```javascript
$(".numeric").on('keypress', function(e){
	return e.which === 8 || e.which === 0 || (e.which >= 48 && e.which <= 57);
});
```
In the original code;

* It returns `false` it the value is numeric. This is very confusing. 
* Only numeric keys are allowed so, rather then letters, also, copying or cutting even deleting the value was forbidden.
