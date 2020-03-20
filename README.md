A description for building web projects with Gulp. Uses Gulp 4.x.

<<<<<<< HEAD
Features

Concatenate, minify, and lint JavaScript.
Compile, minify, autoprefix, and lint Sass.
Optimize SVGs.
Copy static files and folders into your dist directory.
Automatically add headers and project details to JS and CSS files.
Create polyfilled and non-polyfilled versions of JS files.
Watch for file changes, and automatically recompile build and reload webpages.
Gulp Boilerplate makes it easy to turn features on and off, so you can reuse it for all of your projects without having to delete or modify tasks.

Getting Started
Dependencies
Note: if you've previously installed Gulp globally, run npm rm --global gulp to remove it. Details here.

Make sure these are installed first.

Node.js
Gulp Command Line Utility npm install --global gulp-cli
Quick Start
In bash/terminal/command line, cd into your project directory.
Run npm install to install required files and dependencies.
When it's done installing, run one of the task runners to get going:
gulp manually compiles files.
gulp watch automatically compiles files and applies changes using BrowserSync when you make changes to your source files.
Try it out. After installing, run gulp to compile some test files into the dist directory. Or, run gulp watch and make some changes to see them recompile automatically.

Documentation
Add your source files to the appropriate src subdirectories. Gulp will process and and compile them into dist.

JavaScript files in the src/js directory will be compiled to dist/js. Files in subdirectories under the js folder will be concatenated. For example, files in js/detects will compile into detects.js.
Files in the src/sass directory will be compiled to dist/css.
SVG files placed in the src/svg directory will be optimized with SVGO and compiled into dist/svg.
Files and folders placed in the copy directory will be copied as-is into the dist directory.
package.json
The package.json file holds all of the details about your project.

Some information is automatically pulled in from it and added to a header that's injected into the top of your JavaScript and CSS files.

{
	"name": "project-name",
	"version": "0.0.1",
	"description": "A description for your project.",
	"main": "./dist/your-main-js-file.js",
	"author": {
		"name": "YOUR NAME",
		"url": "http://link-to-your-website.com"
	},
	"license": "MIT",
	"repository": {
		"type": "git",
		"url": "http://link-to-your-git-repo.com"
	},
	"devDependencies": {}
}
Note: devDependencies are the dependencies Gulp uses. Don't change these or you'll break things. If any of the other fields are removed, make sure to remove reference to them in the Header (under var banner in gulpfile.js) or gulp watch won't run.

JavaScript
Put your JavaScript files in the src/js directory.

Files placed directly in the js folder will compile directly to dist/js as both minified and unminified files. Files placed in subdirectories under src/js will also be concatenated into a single file. For example, files in js/detects will compile into detects.js.

A note about polyfills: In subdirectories that contain files with the .polyfill.js suffix (for example, _matches.polyfill.js), two versions will be created: one with the polyfill files, and one without.

Sass
Put your Sass files in the src/sass directory.

Gulp generates minified and unminified CSS files. It also includes autoprefixer, which adds vendor prefixes for you.

SVGs
Place SVG files in the src/svg directory.

SVG files will be optimized with SVGO and compiled into dist/svg.

Copy Files
Files and folders placed in the src/copy directory will be copied as-is into dist.

This is a great place to put HTML files, images, and pre-compiled assets.

Options & Settings
Gulp Boilerplate makes it easy to customize for projects without having to delete or modify tasks.

Options and settings are located at the top of the gulpfile.js.

Settings
Set features under the settings variable to true to turn them on (default), and false to turn them off.

/**
 * Settings
 * Turn on/off build features
 */

var settings = {
	clean: true,
	scripts: true,
	polyfills: true,
	styles: true,
	svgs: true,
	copy: true,
	reload: true
};
Paths
Adjust the input and output paths for all of the Gulp tasks under the paths variable. Paths are relative to the root project folder.

/**
 * Paths to project folders
 */

var paths = {
	input: 'src/',
	output: 'dist/',
	scripts: {
		input: 'src/js/*',
		// polyfills: '!src/js/*.polyfill.js',
		polyfills: '.polyfill.js',
		output: 'dist/js/'
	},
	styles: {
		input: 'src/sass/**/*.{scss,sass}',
		output: 'dist/css/'
	},
	svgs: {
		input: 'src/svg/*.svg',
		output: 'dist/svg/'
	},
	copy: {
		input: 'src/copy/*',
		output: 'dist/'
	},
	reload: './dist/'
};
Header
Gulp auto-injects a header into all of your JavaScript and CSS files with details from your package.json file.

You can change what's included under the banner variable.

/**
 * Template for banner to add to file headers
 */

var banner = {
	full:
		'/*!\n' +
		' * <%= package.name %> v<%= package.version %>\n' +
		' * <%= package.description %>\n' +
		' * (c) ' + new Date().getFullYear() + ' <%= package.author.name %>\n' +
		' * <%= package.license %> License\n' +
		' * <%= package.repository.url %>\n' +
		' */\n\n',
	min:
		'/*!' +
		' <%= package.name %> v<%= package.version %>' +
		' | (c) ' + new Date().getFullYear() + ' <%= package.author.name %>' +
		' | <%= package.license %> License' +
		' | <%= package.repository.url %>' +
		' */\n'
};
=======
>>>>>>> 68cd78dbf8bd8354acba68e877a12a4628344226
