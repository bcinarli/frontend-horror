# Buttons/Links
These samples are a collection of button and/or anchor elements' bad practices which were _really_ implemented in production as some point!

## Save Button
There was a button block which consist of 6 different HTML elements. Probably, the developer tried to build a cross-browser "rounded" shape button with different `div` elements. However, this rounded shape can also achieved with `:before` and `:after` pseudo elements.

### How was it?
```html
<div class="btnWrapper">
	<a href="javascript:_doPostBack('same params');" onclick=";reValidate('');;" id="ct100_theNavigationButtons_ct102" class="linkbutton">
    	<div class="saveBtn active">
        	<div class="saveLeft"></div>
            <div class="saveMiddle">Save</div>
            <div class="saveRight"></div>
        </div>
    </a>
</div>
```

### How could it be, plausible better solution(s)? 
```html
<a href="/save" class="link-button save-button">Save</a>
```

With the right and simplier usage, the code is more clearer and easily controllable with css.