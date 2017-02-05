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
{% highlight javascript %}
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
{% endhighlight %}

Trying ES6 syntax with Babel:
{% highlight javascript %}
  //ES6
  [1,2,3].map(x => x * x);

  //ES5
  [1, 2, 3].map(function (x) {
  return x * x;
});
{% endhighlight %}


Grunt automation ROCKS!:
{% highlight javascript %}
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
{% endhighlight %}

### Day 3: 05 Feb 2017

**Today's Progress:** Started a completely [fresh Jekyll x Bootstrap website](https://d0ct0r4r6a.github.io/Playground-Bootstrap-4/). It will serve as my practice ground and inspiration dump point for Bootstrap 4. I am also going through Jekyll docs verbatim.

**Thoughts:** Jekyll's Liquid rendering engine is something. I guess I will have to play around with Jekyll some more to get used to it. Tried using Bower and npm (and Grunt) for the new website, but they messed up my directories. Need to experiment with the workflow and see what others do.

**Screenshots:**

![Playground · Bootstrap 4 initial directories](img/d3-1.png)

*Playground · Bootstrap 4 directories*

**Code Snippets:**

In my _config.yml:
```yml
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

## About #100DaysofCode
* [Rules](rules.md)
* [Previous Log: my first run – ended on the 8th day ](previous-log.md)
* [FAQ](FAQ.md)
* [Resources](resources.md)
