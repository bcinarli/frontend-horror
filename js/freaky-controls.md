## Freaky Controls
These samples are a collection of extremely wrong-way implemented controls which were really used in production as some point!

### If it is `false` then it is `true`!
The case was, allowing only numeric values in an input. The function checks the value, then returns __false__ _if the value is numeric_ (O.o)

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

$(".numeric").keypress(function(e){
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
    return e.which === 8 || e.which === 0 || (e.which >= 48 && e.which <= 57);
});
```
In the original code;

* It returns `false` it the value is numeric. This is very confusing. 
* Only numeric keys are allowed so, rather then letters, also, copying or cutting even deleting the value was forbidden.
