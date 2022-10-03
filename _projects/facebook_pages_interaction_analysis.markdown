---
layout: page
title: Facebook pages interaction analysis and data scraping
description: # A simple project, where I scraped data about 
img: /assets/img/interactive_graph_labeled.png
importance: 3
category: fun
---

This project is concerned with extracting data from Facebook pages and mining their divergent attitudes towards climate 
change. 
The project is part of my girlfriend's thesis, where I helped with scraping the data and then processing it.
As the code was not expected to be reused, not much care was given to its cleanliness and readability (tbh, it is ugly). 😥
The thesis is available [here](https://dspace.cuni.cz/handle/20.500.11956/148143?locale-attribute=en), unfortunately 
only in Czech.
The English abstract is available 
[here](https://dspace.cuni.cz/bitstream/handle/20.500.11956/148143/120399369.pdf?sequence=3&isAllowed=y).
In short, the thesis tries to indirectly analyze Facebook's page recommendation algorithm and its effect on the creation 
of information bubbles in relation to the climate crisis.


## Summary of steps

1. For each initially selected site (there were 20 in total), all recommended pages were scraped
2. Step 1. was repeated also for the scraped pages, i.e., two rounds of scraping was done
3. Pages that was not relevant to climate change were removed. We used a custom tf-idf-like score and hand-picked threshold
4. Rest of the climate change-related pages were manually annotated, i.e., their attitude towards climate change
5. A simple analysis of these annotated pages and their relationships was performed to see if FB's recommendation algorithm helps with breaking information bubbles


## Result

It's not that bad. FB is trying to recommend non-climate change denial pages a little more often.


## Future work

There is a plenty of space for improvement. 
Some simplifying assumptions were used in this project, for example, each of the recommended pages is considered to be equivalent.
However, to get to the last recommended page, the user has to click through. 
So, obviously, those are not equivalent and should be reweighted.


## Code

Code is provided [here](https://github.com/ryparmar/fb-related-pages).


## Visualization of data sample using Bokeh library

<iframe
  src="/assets/visualizations/interactive_graph_labeled.html"
  style="width:107%; height:825px;"
></iframe>

<!-- Every project has a beautiful feature showcase page.
It's easy to include images in a flexible 3-column grid format.
Make your photos 1/3, 2/3, or full width.

To give your project a background in the portfolio page, just add the img tag to the front matter like so:

    ---
    layout: page
    title: project
    description: a project with a background image
    img: /assets/img/12.jpg
    ---



<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/1.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/3.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/5.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    Caption photos easily. On the left, a road goes through a tunnel. Middle, leaves artistically fall in a hipster photoshoot. Right, in another hipster photoshoot, a lumberjack grasps a handful of pine needles.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/5.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>

You can also put regular text between your rows of images.
Say you wanted to write a little bit about your project before you posted the rest of the images.
You describe how you toiled, sweated, *bled* for your project, and then... you reveal it's glory in the next row of images.


<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/6.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/11.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>


The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/" target="_blank">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

```html
<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/6.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/11.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
``` -->
