jQuery Raphael Gauge
=============
[![Code Climate](https://codeclimate.com/github/wasilak/angular-raphael-gauge/badges/gpa.svg)](https://codeclimate.com/github/wasilak/angular-raphael-gauge)

You can see demo [here](http://wasilak.github.io/angular-raphael-gauge/).

Why bother?
-------------------
I needed this kind of Gauge "chart" for one of my projects and it was great opportunity to get some experience in both AngularJS and Raphael.js :)

INSTALLATION
-------------------

via bower:

```
bower install angular-raphael-gauge
```

or simply download latest source code from repository: [link](https://github.com/wasilak/angular-raphael-gauge/archive/master.zip)

USAGE
-------------------

Include ```angular-raphael-gauge``` in your HTML file. Remember about including [Raphael.js](http://raphaeljs.com/) and [jQuery]().

```html
<!-- AngularJS -->
<script src="path/to/angular.min.js"></script>

<!-- JQuery -->
<script src="path/to/jquery.min.js"></script>

<!-- Raphael.js -->
<script src="path/to/raphael-min.js"></script>

<!-- angular raphael gauge -->
<script src="path/to/angular-raphael-gauge.min.js"></script>
```

Next plugin-in ```angular-raphael-gauge``` into your application:

```javascript
var angularDemo = angular.module('angularDemo', ['angular-raphael-gauge']);
```

Now all you have to do is put directive code into HTML file:
```javascript
<raphael-gauge id="gauge1" config="gauge"></raphael-gauge>
```

and pass some options via config object in ```$scope```:
```javascript
angularDemo.controller('DemoCtrl', ['$scope', function ($scope) {
  $scope.gauge = {
          name: 'Some data',
          opacity: 0.55,
          value: 65,
          text: 'some cool data'
        };
}]);
```

Updating ```$scope.value``` will update gauge value and render animation.

That's it! :) See [demo](http://wasilak.github.io/angular-raphael-gauge/) for working example.

OPTIONS
-------------------

Here are options available to be set during runtime:

```javascript
var options = {
              name: false,  // text under gauge
              value: 25,    // value
              image: false, // path to image (should be square) - it will be under gauge
              text: false,  // text in the middle of gauge
              textColor: '#000000', // text color
              arcColor: '#57E0EA',  // animated arc color
              bgArcColor: '#000',   // round background under arc
              opacity: false,   // arc opacity
              duration: 1600,   // animation duration
              easing: 'bounce' // Raphael easing effect. Don't use backIn or Elastic, they mess up animation :/
            };
 ```

Building / Minifing
----------

You can build minified version yourself, by simply using [Grunt](http://gruntjs.com) in project root.

```bash
grunt
```

Contributing
--------------

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
