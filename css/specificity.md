## Specificity
These samples are a collection of CSS specifity bad practices which were really implemented in production as some point!

### Building a Train
CSS preprocessor and nesting mostly helpful, but sometimes, you get an overkill :/

#### How it was
```SCSS
.front {    
	.slider-content {
    	width:960px;
        
    	.column {
        	text-align: center;
            
          	figure {
            	position:relative;
          		width:228px;
          		height:362px;
            
            	figcaption {
                	position:absolute;
              		bottom: 0;
            		left:0;
            		width:100%;
            		height:140px;
                
                	h1 {
                    	line-height:1em;
              			font-size: 20px;
                  	}
              	}
          	}
        }
    }
}

// from outer to inner, you get more specific selector chain
// which for the very inner h1 element you get a selector like
// .front .slider-content
// .front .slider-content .column
// .front .slider-content .column figure
// .front .slider-content .column figure figcaption
// .front .slider-content .column figure figcaption h1 { wtf (X.X) }
```

#### How it should be?
```CSS
.front-slider-content {
	width: 960px;
}

.front-slider-column {
	text-align: center;
}

.front-slider-figure {
	position: relative;
    width: 228px;
    height: 362px;
}

.front-slider-caption {
	position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 140px;
}

.front-slider-captiontitle {
	line-height: 1em;
    font-size: 20px;
}
```
Instead of nesting elements in Sass/Less, adding classes according to their identification, you get only one selector for each element. 

Also, for this example, different approaches in the HTML part could also help to simplify CSS definitions