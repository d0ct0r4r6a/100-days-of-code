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

Trying ES6 syntax with Babel:
```javascript
  //ES6
  [1,2,3].map(x => x * x);

  //ES5
  [1, 2, 3].map(function (x) {
  return x * x;
});
```

Grunt automation ROCKS!:
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

## About #100DaysofCode
* [Rules](rules.md)
* [Previous Log: my first run – ended on the 8th day ](previous-log.md)
* [FAQ](FAQ.md)
* [Resources](resources.md)
