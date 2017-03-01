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

### Day 7: 10 Feb 2017

**Today's Progress:** Breaking the [rules](rules.md) here, but today I was only following tutorials in [this playlist](https://www.youtube.com/playlist?list=PL4cUxeGkcC9gcy9lrvMJ75z9maRw4byYp).

**Thoughts:** I should have spent an hour really focusing on my projects then I would watch / do any tutorials. Anyway, I got the gist of NodeJS and Express now. Is it just me or Express feels like Jekyll but with extra capabilities such as it can use Javascript to extend its Views templates. Like Jekyll + PHP + JS => Express

**Tips:** Use [nodemon](https://nodemon.io/) during NodeJS development. The [jekyll-livereload](https://github.com/RobertDeRose/jekyll-livereload) equivalent in NodeJS. 

**Code Snippets:**

My first Express app:

{% highlight javascript %}
```javascript
var express = require('express');
var bodyParser = require('body-parser');


var app = express();

var urlencodedParser = bodyParser.urlencoded({ extended: false });

app.set('view engine', 'ejs');
app.use('/assets', express.static('assets')); 

app.get('/', function(req, res){
  res.render('index');
});

app.get('/contact', function(req, res){
  
  res.render('contact', {qs : req.query});
});

app.post('/contact', urlencodedParser, function(req, res){
  console.log(req.body);
  res.render('contact-success', {data: req.body});
});

app.get('/profile/:name', (req,res)=>{
  var data = {
    age: 29, 
    job: 'developer',
    hobbies: ['eating','fighting','singing']
  };
  res.render('profile', {person: req.params.name, data: data})
});

app.listen(3000);
```
{% endhighlight %}

An embeddedJS template, see what I meant by Jekyll + PHP + JS:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title><%= person %>'s profile</title>
  <link rel="stylesheet" href="/assets/styles.css">
</head>
<body>
  <% include partials/nav.ejs %>
  <h1>Welcome to the profile of <%= person %></h1>
  <p><strong>Age: </strong><%= data.age %></p>
  <p><strong>Job: </strong><%= data.job %></p>
  <ul>
    <% data.hobbies.forEach(function(item){ %>
      <li><%= item %></li>
    <% }); %>
  </ul>
</body>
</html>
```

### Day 8: 11 Feb 2017

**Today's Progress:** Created a [To-do list app](https://github.com/d0ct0r4r6a/To-Do-NodeJS-App).

**Thoughts:** The feeling of completing something is amazing. Learned about connecting Express app to MongoDB with Mongoose as the driver and mLab as the database host. AJAX is a powerful tool, really.

### The 2-week hiatus

Ah... Please forgive me. 2 whole weeks without coding at all? What am I thinking? Truth is, I moved from my hometown to the bustling capital, Jakarta. This is not really an excuse since 1-hour of coding could easily be done by some unemployed guy like me who has almost the whole day. Hahahaha.

Anyway, I have been learning something new everyday. I got my hands on Linux server setup, Excel VBA scripting, and other stuff. Hahhaha let me resume this log now..

Trivia: The last log also stopped on the 8th entry. Hmm what's with the number 8?

### Day 9: 25 Feb 2017

**Today's Progress:** Built more familiar layout for [Playground &middot; Bootstrap 4](https://d0ct0r4r6a.github.io/Playground-Bootstrap-4/). Also started brainstorming for the first element on the site, the jumbotron.

**Thoughts:** I just learned the CSS `animation` fundamentals. I wonder if I could use it on the Playground &middot; Bootstrap4 site.

### Day 10: 26 Feb 2017

**Today's Progress:** Playing around with CSS animation; creating sliding box. On the other hand, learned how to integrate PostCSS to my workflow.

**Thoughts:** Hmm PostCSS has a lot of plugins. Where to start?

### Day 11: 27 Feb 2017

**Today's Progress:** Spent the whole day watching tutorials. Learned a whole bunch about setting up reproducible build using Jake.

**Thoughts:** Okay, so we have Jake, Grunt, and Gulp. JS is full of choices, eh.

**Extra:** A cool interactive game for learning Git. [learngitbranching.js.org](http://learngitbranching.js.org)

**Code Snippets:**

{% highlight javascript %}
```javascript
desc("Check external dependencies");
  task("version", ()=>{
    console.log("Checking dependencies...");

    const EXPECTED_NODE_VERSION = packageJson.engines.node;
    let actualVersion = process.version;

    if ( semver.neq(EXPECTED_NODE_VERSION,actualVersion) )
      fail(`Incorrect Node version: expected ${EXPECTED_NODE_VERSION} , but was ${actualVersion}`);
  });

  desc("Lint JavaScript code");
  task("lint", ()=>{
    process.stdout.write("Linting JavaScript: ");

    jshint.checkFiles({
      files: ["Jakefile.js", "src/**/*.js"],
      options: {},
      globals: {}
    },complete, fail);
    // without simplebuild-jshint, run jshint from command line
    // jake.exec("node node_modules/jshint/bin/jshint Jakefile.js", {interactive: true}, complete);
  },{ async: true });
```
{% endhighlight %}

### Day 12: 28 Feb 2017

**Today's Progress:** Learned TDD JavaScript development. Again, following tutorials.

**Thoughts:** Chai + Mocha + Karma = Testing Trio. There should have been more of JS testing utilities, knowing how JS community is.

**Code Snippets:**

{% highlight javascript %}
```javascript
desc("Start the Karma server. [START THIS FIRST]");
  task("karma", ()=>{
    console.log("Starting karma server...");
    karma.start({
      configFile: KARMA_CONFIG
    }, complete, fail);
  }, {async: true});

  desc("Default build");
  task("default",["version","lint","test"], ()=>{
    console.log("\nBUILD SUCCESS");
  });
```
{% endhighlight %}

### Day 13: 01 Mar 2017

**Today's Progress:** Learned how to use Modernizr to detect browser features. I also played learngitbranching.com until remoteAdvanced5 level.

**Thoughts:** Phew. There are a lot of things to juggle in developing a webapp, huh.

**Not coding, but...:** I was preparing my interview tomorrow for a Junior Business Analyst position in BCA. So half of the day I was just browsing their apps and reviewing software dev practices.

## About #100DaysofCode
* [Rules](rules.md)
* [Previous Log: my first run – ended on the 8th day ](previous-log.md)
* [FAQ](FAQ.md)
* [Resources](resources.md)
