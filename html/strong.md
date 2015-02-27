# Should \<strong\>, \<em\> elements be styled?

### How was it?
```html
<div class="answer-result">
    <strong class="result is-empty">
        <span class="detail">Some Text</span>
    </strong>
</div>
```

### How could it be? (maybe)
```html
<div class="answer-result result is-empty">
	<span class="detail"><strong>Some Text</strong></span>
</div>
```