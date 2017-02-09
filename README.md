# 100 Days Of Code - Log

### Day 1: 03 Feb 2017

**Today's Progress:** Revamped my Github page using Jekyll with Hyde theme.

**Thoughts:** Different Jekyll themes have different layout coding style —
further complicating content insertion. Tried using Bootstrap but ended 
distorting all the styles. 

**Link to work:** [Day 1](http://d0ct0r4r6a.github.io)

### Day 2: 04 Feb 2017

**Today's Progress:** Dipped into Angular, Grunt-cli, and ES6 with Babel-cli.

**Thoughts:** Grunt just completely blew my mind. Angular also gave [a good quick-start](https://angular.io/docs/ts/latest/quickstart.html) and explanation to its Component-based framework. And finally, getting the hang of [ES6 arrow function](https://www.sitepoint.com/es6-arrow-functions-new-fat-concise-syntax-javascript/).

**Code Snippets:** 

My first Angular Component:

{% highlight javascript%}
```javascript
(function (app) {
  app.AppComponent =
    ng.core.Component({
      selector: 'my-app',
      template: `<h1>Hello Angular. This is Arga.</h1>
      <ul> 
        <li>Hi</li>
        <li>Another Hi</li>  
      </ul>`
    })
      .Class({
        constructor: function () { }
      });
})(window.app || (window.app = {}));
```
{% endhighlight %}

Trying ES6 syntax with Babel:
{% highlight javascript%}
```javascript
  //ES6
  [1,2,3].map(x => x * x);

  //ES5
  [1, 2, 3].map(function (x) {
  return x * x;
});
```
{% endhighlight %}


Grunt automation ROCKS!:
{% highlight javascript%}
```javascript
module.exports = function (grunt) {
  grunt.initConfig({
    concat: {
      dist: {
        src: ['app/app.module.js', 'app/app.component.js'],
        dest: 'voila.js'
      },
    },
    watch: {
    js: {
      files: ['app/*.js'],
      tasks: ['concat']
      }
    }
  });

  grunt.loadNpmTasks('grunt-contrib-concat');
  grunt.loadNpmTasks('grunt-contrib-watch');

};
```
{% endhighlight %}

### Day 3: 05 Feb 2017

**Today's Progress:** Started a completely [fresh Jekyll x Bootstrap website](https://d0ct0r4r6a.github.io/Playground-Bootstrap-4/). It will serve as my practice ground and inspiration dump point for Bootstrap 4. I am also going through Jekyll docs verbatim.

**Thoughts:** Jekyll's Liquid rendering engine is something. I guess I will have to play around with Jekyll some more to get used to it. Tried using Bower and npm (and Grunt) for the new website, but they messed up my directories. Need to experiment with the workflow and see what others do.

**Screenshots:**

<img src="{{site.baseurl}}img/d3-1.png" alt="Playground · Bootstrap 4 initial directories"/>

*Playground · Bootstrap 4 initial directories*

**Code Snippets:**

In my _config.yml/html :

{% highlight yaml %}
```
# Dev

source: ./            #Default value
destination: ./_site  #Default value
highlighter: rouge
incremental: TRUE
markdown:    kramdown
port: 100 # Port 4000 is used to view Jekyll docs
profile: TRUE

defaults:
  -
    scope:
      path: ""
      type: pages
    values:
      layout: "default"
```
{% endhighlight %}

In my _includes/head.html:

```html
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
  <title>Playground &middot; Bootstrap 4</title>
  <link rel="stylesheet" href="{{site.baseurl}}/css/bootstrap-reboot.min.css">
  <link rel="stylesheet" href="{{site.baseurl}}/css/bootstrap.min.css">
  <link rel="stylesheet" href="{{site.baseurl}}/css/bootstrap-grid.min.css">
  <script src="{{site.baseurl}}/js/bootstrap.min.js"></script>
</head>
```

### Day 4: 06 Feb 2017

**Today's Progress:** Continued building (and experimenting with) [the Jekyll x Bootstrap site](https://d0ct0r4r6a.github.io/Playground-Bootstrap-4/). 

**Thoughts:** [jekyll-livereload](https://github.com/RobertDeRose/jekyll-livereload) plugin is a time-saver. The only pesky thing to deal with (for now) is getting the `site.baseurl` thingy to work with links. Kept restarting the local server. Urgh!

**Tips:** If you like to have Bootstrap 4 quick reference, then the [Bootstrap 4 Cheat Sheet](https://hackerthemes.com/bootstrap-cheatsheet/) is for you. 

**Code Snippets:**

The post.html layout:

```html
<div class="container">
  <div class="row">
    <div class="col-8 offset-2">
      <h1 class="display-4">{{ page.title }}</h1>
      <p class="lead">{{ page.description }}</p>
      <hr>
          {{ content }}
      <a href="{{site.baseurl}}" class="btn btn-outline-primary">Back</a>
    </div>
  </div>
</div>
```
### Day 5: 07 Feb 2017

**Today's Progress:** Started *seriously* learning NodeJS. 

**Thoughts:** I fell sick and couldn't think properly. Only managed to go through the codes in [this playlist](https://www.youtube.com/playlist?list=PL4cUxeGkcC9gcy9lrvMJ75z9maRw4byYp).

### [SICK] : 08 Feb 2017

**Note:** My cold worsens. I can't stand looking at my laptop screen. So I rest for most of the day and prepare for my trip to Singapore tonight. 

### Day 6: 09 Feb 2017

**Today's Progress:** Updated my personal website: [About](https://d0ct0r4r6a.github.io/about/), ][Books](https://d0ct0r4r6a.github.io/books/).

**Thoughts:** Not responsive yet.

**Sponsors:** Check out [this awesome character/story planner](http://bit.ly/2k7yxzh)

## About #100DaysofCode
* [Rules](rules.md)
* [Previous Log: my first run – ended on the 8th day ](previous-log.md)
* [FAQ](FAQ.md)
* [Resources](resources.md)
