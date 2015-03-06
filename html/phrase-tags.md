# Phrase / Semantic Tags
These samples are a collection of phrase tags' bad practices which were _really_ implemented in production as some point!

##`strong` Tag
`strong` tag is used for defining important text. It has a default style of `font-weight: bold;`, but it doesn't meant to be styled. It basically makes the text bold. Adding a class to it should be avoided.

I have come across this code in a project. It has a class and also there is a `span` tag inside. The better usage is not to have any tags inside of phrase tags such as `strong` and `em`.

### How was it?
```html
<div class="answer-result">
    <strong class="result is-empty">
        <span class="detail">Some Text</span>
    </strong>
</div>
```

### How could it be, plausible better solution(s)?
```html
<div class="answer-result result is-empty">
	<span class="detail"><strong>Some Text</strong></span>
</div>
```

Instead of styling the `strong` element with normal text style, just use `span` and wrap the text with `strong` which is going to be bold.