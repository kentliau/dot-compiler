#dot-module

dot-module lets you simple transform your templates directory into one CommonJS module. Best served with [modules-webmake](https://github.com/medikoo/modules-webmake). Some ideas (and the example below) took from [dot-packer](https://github.com/Katahdin/dot-packer).

### Installation:

```	
npm install -g dot-module
```

###Usage:  

```
dot-module -d templates/ -o ./templates.js
```

###Options:

	-d 	Target directory <path>
	-o	Output file <path>
	

###Example:
	
Create a doT.js template (templates/sample.html).  Templates must have a .html extension.

	<ul id="scores">
		{{~it.scores:score:index}}
			<li>{{=score}}</li>
		{{~}}
	</ul>

	dot-packer -d templates/ -o ./templates.js
	
Once you include the templates.js module to your code, you can access the template like this:

```
var templates = require('./templates'),
	scores = templates['scores'];
	
container.innerHTML = scores({
  scores: user.scores
});

```
