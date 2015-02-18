## Freaky Controls
These samples are a collection of interestingly wrong-way implemented controls which were really used in production as some point!

### If `false` then `true`!
The case was, allowing only numeric values in an input. The implementation checks the value but returns false if the value is numeric (O.o)

#### How it was?
```javascript
function isNumeric(num){    
    if(num >= 48 && num <= 57) {
        return false;
    }
    else {
        return true;
    }
}

$(".numeric").on('keydown', function(e){
    if(!isNumeric(e.keyCode)){
        return true;
    }
    else {
        return false;
    }
});
```

#### How it should be?
```javascript
$(".numeric").on('keypress', function(e){
    if (e.which != 8 && e.which != 0 && (e.which < 48 || e.which > 57)) {
		return false;
    }
});
```
In the original code;

* It returns `false` it the value is numeric. This is very confusing. 
* Only numeric keys are allowed so, rather then letters, also, copying or cutting even deleting the value was forbidden.