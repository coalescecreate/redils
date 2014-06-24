# Redils - A HTML slider #

A jQuery plugin that changes any HTML content into a slider or fader. Content should be contained within .slide containers. The slider has pagination (numbers, letters, text), timer, timer bar, arrows, carousel animation, rewind animation and overflow slides so that the next and prev slides can be viewed.

### Usage ###


Initiate with `$(selector).redils({'some':'property'});`   
Invoke methods with `$(selector).redils('method', {'some':'property'});`   
Example

	$('.redils').redils({
		debug: true,
		zIndex: 2000
	})

### HTML ###

Following structure is required for slider to work. (Using Emmet tab complete for HTML)

	div
	div.redils>div.slide-cont[style="width: 7020px"]>div.slides*5>img
	table.redils-controls>tbody>tr>td.arrow-area.arrow-area-left>div.arrow^td.center-cell+td.arrow-area.arrow-area-right>div.arrow
	div.pagination

### Properties ###

#### width ####

*Default* `'dyn'`   
*Expects* `'dyn', integer`

Enables dynamic widths of the slider. Redils works out how wide each slide is.

	$(selector).redils({width: 'dyn'});


#### overflow ####

*Default* `1`   
*Expects* `0, 1, 2`

Show slides around the main slider area. Clones slides to the end and the beginning of the slide container. Also important for using the slider in a carousel way. Infinity loop of slides.

	$(selector).redils({width: 'dyn'});


#### speed ####

*Default* `200`   
*Expects* `integer`

How fast the animation between slides is.

	$(selector).redils({width: 'dyn'});


#### center ####

*Default* `false`   
*Expects* `boolean`

If the container is bigger than the slide it will center the slide.

	$(selector).redils({center: false});


#### pagination ####

*Default* `true`   
*Expects* `boolean, 'num', 'str'`

Adds dynamically created elements to pagination container. Pagination *will only be true* if a sibling to the called container has a container with `.pagination`.   
`'num'` `'str'` prints out consecutive numbers, letters respectively. `data-pagination="String"` can be set on each slide to define indivdual unique pagination names on each slide.
Pagination will create following html structure `div.center-pagination>a*5>span.default-pagination` (default-pagination and 5 are subject to options).

	$(selector).redils({pagination: true});


#### attach ####

*Default* `false`   
*Expects* `false, 'pre', 'post'`

Used in combination with pagination to determine whether or not to add a prefix or suffix to the pagination.

	$(selector).redils({attach: false});


#### fullWidth ####

*Default* `false`   
*Expects* `integer, false`

This makes the slide container fill it's container completely. Integer is the minimum width of the slide container.

	$(selector).redils({fullWidth: false});


#### auto ####

*Default* `4000`   
*Expects* `integer, false`

Integer determines pause length before animating further. False takes away auto animation. Interaction with slider stops animation. To restart it call method resumAnimation.

	$(selector).redils({auto: 4000});


#### autoResize ####

*Default* `false`   
*Expects* `boolean`

Slider resizes based on width of it's container and changes everytime window changes size. Good for stretch resposnsive websites better to handle breakpoint responsive sizing with method update.

	$(selector).redils({autoResize: false});


#### multiSlide ####

*Default* `false`   
*Expects* `boolean, 'centered'`

Property under construction. Should not be used.

	$(selector).redils({multiSlide: false});


#### slide ####

*Default* `false`   
*Expects* `boolean`

Should only be used if the plugin is already being used or if you want to switch between the two. Collapses the slider so that the slides are lying on top of each other and has a fade transition.

	$(selector).redils({slide: false});


#### debug ####

*Default* `false`   
*Expects* `boolean`

Sets debug mode on, should be off for production.

	$(selector).redils({debug: false});


#### Classes ####

Numerous classes can be reassigned. Check the `defaultOpts {}` as to which classes are able to be manipulated.


### Methods ###

#### update ####

Run update when the slider has changed size that requires the recalculation of positions and size widths.

	$(selector).redils('update');


#### pauseAnimation ####

Used to pause animation i.e. onmousenter of container pause animation.

	$(selector).redils('pauseAnimation');


#### resumeAnimation ####

Used to resume animation i.e. onmouseleave of container resume animation.

	$(selector).redils('pauseAnimation');


#### skipTo ####

Define outside of the plugin container which slide to skip to. 

	$(selector).redils('skipTo');


### Changelog ###

**Version 1.4.0**   
Auto resize now updates the size of the slider based on parent container's width and ratio of slides. Using naturalWidth/naturalHeight

**Version 1.3.4**   
Tidying up resize of the slider added an option to have the resize decided by the plugin or from outside.

**Version 1.3.3**   
Added 1px to each slide to account for subpixels.

**Version 1.3.2**   
Fixed a few bugs regarding resizing the slider and updating slide widths.

**Version 1.3.1**   
If on interaction slider stops, if on pause or resume slider continues only if it hasn't been interacted with.

**Version 1.3**   
Added a new method skipToSlide.

**Version 1.2.1**   
Added a small fix for pagination pre/post so if there is no data tag and it returns undefined it isn't printed.

**Version 1.2**   
Added in pause and resume animation

**Version 1.1**   
Individual pagination menu items
Full width slides
Fix on update

**Version 1.0**  
Basic slider finished.



### Development ###

**Requirements**
* This plugin requires [node](http://nodejs.org/), [gulpjs](http://gulpjs.com/) and [bower](http://bower.io/).
* Follow JSCS guidelines a styling-example.js is also included.
* Run `bower install` and `npm install` to get dev dependencies. Bower and Gulp is assumed to be running globally.

### Contact ###

This is a small plugin by Young Skilled.
Contact [richard](mailto:richard@youngskilled) for more details about this plugin.