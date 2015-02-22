# Extreme Grouping
These samples are a collection of Selector Grouping bad practices which were really implemented in production at some point!

## Group Similar Definitions Together!
This was not very clear if it was a Sass/Less output or written by hand. But either way, these selectors are pretty awful. This is also a "[Specificity](specificity.md)" sample.

### How was it?
```css
.cover-2 .main .nav .remove-area,
.cover-2 .main .photo .remove-area,
.cover-2 .main .topic .remove-area,
.cover-2 .main .text .remove-area,
.cover-2 .main .controls .remove-area,
.cover-2 .main .video .remove-area,
.cover-2 .main .update-video .remove-area,
.cover-2 .main .update-cover .remove-area
{
	display: none;
    font-family: "MavenProRegular", sans-serif;
    position: absolute;
    width: 150px;
    padding: 0;
    height: 50px;
    right: -135px;
    top: 30px;
    color: #373737;
    z-index: 33;
}

.cover-2 .main .nav .remove-area button,
.cover-2 .main .photo .remove-area button,
.cover-2 .main .topic .remove-area button,
.cover-2 .main .text .remove-area button,
.cover-2 .main .controls .remove-area button,
.cover-2 .main .video .remove-area button,
.cover-2 .main .update-video .remove-area button,
.cover-2 .main .update-cover .remove-area button
{
    font-family: "MavenProBold", sans-serif;
    font-size: 13px;
    background-color: #efe654;
    padding: 10px 15px;
    border: none;
    color: #373737;
}

.cover-2 .main .nav .remove-area button i,
.cover-2 .main .photo .remove-area button i,
.cover-2 .main .topic .remove-area button i,
.cover-2 .main .text .remove-area button i,
.cover-2 .main .controls .remove-area button i,
.cover-2 .main .video .remove-area button i,
.cover-2 .main .update-video .remove-area button i,
.cover-2 .main .update-cover .remove-area button i,
.cover-2 .main .nav .remove-area button b,
.cover-2 .main .photo .remove-area button b,
.cover-2 .main .topic .remove-area button b,
.cover-2 .main .text .remove-area button b,
.cover-2 .main .controls .remove-area button b,
.cover-2 .main .video .remove-area button b,
.cover-2 .main .update-video .remove-area button b,
.cover-2 .main .update-cover .remove-area button b {
	vertical-align: middle;
}

.cover-2 .main .nav .remove-area button i,
.cover-2 .main .photo .remove-area button i,
.cover-2 .main .topic .remove-area button i,
.cover-2 .main .text .remove-area button i,
.cover-2 .main .controls .remove-area button i,
.cover-2 .main .video .remove-area button i,
.cover-2 .main .update-video .remove-area button i,
.cover-2 .main .update-cover .remove-area button i {
	margin-right: 10px;
    margin-bottom: 2px;
}
```

### How could it be, plausible better solution(s)? 
#### First Approach
```css
.cover-2 .remove-area {
	position: absolute;
    top: 30px;
    right: -135px;
    z-index: 33;
    display: none;
    width: 150px;
    height: 50px;
    font-family: "MavenPro", sans-serif;
    color: #373737;
}

.cover-2 button {
	padding: 10px 15px;
    border: none;
    background-color: #efef654;
    font-size: 13px;
    font-weight: bold;
    color: #373737;
}

.cover-2 button i,
.cover-2 button b {
	vertical-align: middle;
}

.cover-2 button i {
	margin-right: 10px;
    margin-bottom: 2px;
}
```
In first approach, since these blocks seem all have the similar elements, it will be clear to select only the target element. Rather than selecting all the way from parent to child, just select the desired element.

Also, in the font-face definitions using 'style linking' will provide you just defining `font-weight` or `font-style` instead of adding each font type's `font-family` for each code block.

#### Second Approach
```css
.cover-remove-area {
	/** add code block **/
}

.cover-button {
	/** add code block here **/
}

.cover-button-icon,
.cover-button-b {
	/** add code block here **/
}

.cover-button-icon {
	/** add code block here **/
}
```
The second approach will give you clearer selectors and improve the reusability of your definitions.