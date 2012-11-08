# JCarousellite

jCarousel Lite is a jQuery plugin that carries you on a carousel ride filled with images and HTML content. Put simply, you can navigate images and/or HTML in a carousel-style widget. It is super light weight, at about 2 KB in size, yet very flexible and customizable to fit most of our needs.

Did I mention that it weighs just 2 KB?

As if that wasn't enough, the best part is yet to come... You don't need any special css file or class name to get this to work. Include the js file. Supply the HTML markup ("div" enclosing an "ul"). Then, construct the carousel with just a simple function call. It is all explained in the installation section. Don't forget to check out the demo for more details or just download now and play with it.

If you have any questions, suggestions, recommendations, requests,..., you can either leave a comment in this blog entry, or you can find me lurking around the jQuery mailing list.

# Why? - We have a jCarousel plug-in already

Ofcourse you do, and yes, jCarousel is a great plug-in. It offers a host of features and it is so customizable that you are limited only by your imagination.

jCarousel Lite is not a replacement for jCarousel; rather it is a light-weight alternative for users (like me) whose primary focus is not to build a full-blown image gallery. For instance, my use-case needed a very simple carousel widget that was going to sit in one corner of the screen. Not much customizations were needed. I figured that jCarousel, with all its options was kinda overkill. So, i started developing my own mini carousel, and you are right now looking at the 1.0 version of the same.

# Documentation

A basic carousel can be constructed with just the following snippet of code. This code is typically executed on document.ready or window.load event, but you can fire the call whenever it is appropriate for your use-case. The following example fires it on document.ready event.

	$(function() {
	    $(".anyClass").jCarouselLite({
	        btnNext: ".next",
	        btnPrev: ".prev"
	    });
	});
    
All the possible customizations are discussed in the section that follows

## Options

### btnPrev

Selector for the "Previous" button. The navigation buttons - both prev and next - need not be as part of the carousel "div" itself, but it can be if you want it to. Where ever you decide to place those buttons in the HTML structure, an appropriate jQuery selector for the "previous" button should be provided as the value for this option.

### btnNext

Selector for the "Next" button. The navigation buttons - both prev and next - need not be as part of the carousel "div" itself, but it can be if you want it to. Where ever you decide to place those buttons in the HTML structure, an appropriate jQuery selector for the "next" button should be provided as the value for this option.

### btnGo

If you don't want next and previous buttons for navigation, instead you prefer custom navigation based on the item number within the carousel, you can use this option. Just supply an array of selectors for each element in the carousel. The index of the array represents the index of the element. What i mean is, if the first element in the array is ".0", it means that when the element represented by ".0" is clicked, the carousel will slide to the first element and so on and so forth. This feature is very powerful. For example, i made a tabbed interface out of it by making my navigation elements styled like tabs in css. As the carousel is capable of holding any content, not just images, you can have a very simple tabbed navigation in minutes without using any other plugin. The best part is that, the tab will "slide" based on the provided effect. :-)

### mouseWheel

As of version 0.4.0, the navigation buttons are no more needed to enjoy the carousel. The mouse-wheel itself can be used for navigation. To achieve this, 2 things should be done. First, include the mousewheel plugin (checkout the installation section). Second, set "true" for this option. That's it, now you will be able to navigate your carousel using the mouse wheel. Using buttons and mouse-wheel are not mutually exclusive. You can still have buttons for navigation as well. They complement each other. To use both together, just supply the btnNext/btnPrev or btnGo options.

### auto

As of version 0.4.0, the carousel can auto-scroll as well. This is enabled by specifying a millisecond value to this option. The value you specify is the amount of time between 2 consecutive slides. The default is null, and that disables auto-scrolling. Specify this value and watch your carousel magically scroll.

### speed

Specifying a speed will slow-down or speed-up the sliding speed of your carousel. Try it out with different speeds like 800, 600, 1500 etc. Providing 0, will remove the slide effect.

### easing

You can specify any easing effect. Note: You need easing plugin for that. Once specified, the carousel will slide based on the provided easing effect.

### vertical

Determines the direction of the carousel. true, means the carousel will display vertically. The next and prev buttons will slide the items vertically as well. The default is false, which means that the carousel will display horizontally. The next and prev items will slide the items from left-right in this case.

### circular

Setting it to true enables circular navigation. This means, if you click "next" after you reach the last element, you will automatically slide to the first element and vice versa. If you set circular to false, then if you click on the "next" button after you reach the last element, you will stay in the last element itself and similarly for "previous" button and first element.

### visible

This specifies the number of items visible at all times within the carousel. The default is 3. You are even free to experiment with real numbers. Eg: "3.5" will have 3 items fully visible and the last item half visible. This gives you the effect of showing the user that there are more images to the right.

### start

You can specify from which item the carousel should start. Remember, the first item in the carousel has a start of 0, and so on.

### scroll

As of version 0.4.0, you can specify the number of items to scroll when you click the next or prev buttons. Ofcourse, this applies to the mouse-wheel and auto-scroll as well. For example, scroll:2 will scroll 2 items at a time.

### beforeStart

Callback function that should be invoked before the animation starts. The elements representing the items that are visible before the animation is passed in as argument.

### afterEnd

Callback function that should be invoked after the animation ends. The elements representing the items that are visible after the animation ends are passed in as argument.