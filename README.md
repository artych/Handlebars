# Atom and Sublime Text 2 / 3 Handlebars.js bundle

- Colours of Handlebars expressions are selected to be in contrast with the surrounding HTML.
- Handlebars expressions get syntax highlighting in HTML attributes.
- Parameters passed to block expressions get syntax highlighting too.
- Works both with individual template files and inline templates in script tags.
- Key bindings for `{{! Handlebars comments }}` (Sublime only)
- Tab triggers for
  - `if` → `{{#if }}`
  - `ifel` → `{{#if }} {{else}}`
  - `el` → `{{else}}`
  - `un` → `{{#unless }}`
  - `ea` → `{{#each }}`
  - `wi` → `{{#with }}`
  - `par` → `{{> }}` (for partials)
  - `x-temp` → `<script type="text/x-handlebars" data-template-name="$1">` (inline script tag in HTML files using the Ember recommended `data-template-name` attribute)
  - `x-id` → `<script type="text/x-handlebars-template" id="$1">` (inline script tag in HTML files using the legacy `id` attribute)

## About Handlebars.js

It's a great JavaScript templating engine, based on [Mustache](http://mustache.github.com/), but amongst others adding the ability to precompile templates and to create custom helpers.

Official website: [handlebarsjs.com](http://handlebarsjs.com/)

## Sublime Text installation

Get it through [Sublime Package Control](http://wbond.net/sublime_packages/package_control).

If you haven't used it yet, just install it from the link above and then:

1. Press Shift + Command (or Control) + P
2. Type "install", to bring up the "Package Control: Install Package" option, and press Enter
3. Look for "Handlebars", and press Enter to install it.
4. Choose "Handlebars" in the bottom right corner with one of your template files open (or in case you have inline templates use Handlebars instead of HTML, it's gracefully extending it so you shouldn't lose anything)
5. Profit

Package Control will also auto-update the package from this point on!

## Atom installation

1. Open Preferences > Install
2. Type "Handlebars" into the search field
3. Click the Install button

## Testing / contribution

I've recently stopped heavily using Handlebars at my day job and became a father, so any contributions are more than welcome! I'm still using Github so will make sure to keep on being responsive on issues and pull requests.

There are some sample templates in `test/` folder. It's possible to see the different supported and yet to be implemented use cases there.

### Sublime Text

If you want to work on the package you should install AAAPackageDev either [from Github](https://github.com/SublimeText/AAAPackageDev) or from Package Control. With that you can edit the JSON version (`grammars/Handlebars.json`) and let it export the Plist (`grammars/Handlebars.tmLanguage`) with the ST Build System.

The nicest development setup I found so far is to have the package installed via Package Control and then symlinking the development Git repo to `Sublime settings folder > Packages`, which then overrides the installed one so you can toggle between them easily.

Another great trick I found out about recently is the `Show scope name` shortcut (Shift + Control + P (OSX) or Shift + Control + Alt + P (Windows)) which will display the language scope on the status bar based on where your cursor is. If you're getting tired of pressing all these keys all the time, there are a few brilliant packages which do this automatically like the more subtle [ScopeAlways](https://sublime.wbond.net/packages/ScopeAlways) or the full on [ScopeHunter](https://sublime.wbond.net/packages/ScopeHunter) – note: both need to be activated via the Command Palette.

Resources on ST / Textmate syntax definitions:

http://docs.sublimetext.info/en/latest/extensibility/syntaxdefs.html
http://manual.macromates.com/en/language_grammars

### Atom

To see what scope Atom detects under the keyboard cursor, press Option + Cmd + P.

TODO: add contribution notes  
TODO: add proper testing based on https://github.com/atom/language-mustache

## Precompilation

This package does not offer any Handlebars precompilation functionality to keep things simple, but you can use [Guard](https://github.com/guard/guard) (which is a file system watcher) and [Guard-Steering](https://github.com/guard/guard-steering) (a Handlebars precompiler from yours truly) to have all templates precompiled as you save them.

There's also a [Guard package for Sublime](https://github.com/cyphactor/sublime_guard) if you want integration, but I don't personally use this as I'm happy with Guard running in an iTerm window I can access from anywhere.

There are of course Node.js / Grunt / Gulp based compilers too ([like this](https://npmjs.org/package/grunt-handlebars-js) and [this](https://www.npmjs.com/package/gulp-compile-handlebars)), but I haven't personally used any yet for precompilation.

## Credits

Adapted from the great [sublime-text-handlebars](https://github.com/nrw/sublime-text-handlebars) package by Nicholas Westlake.

Thanks a lot to all the generous contributors (in alphabetical order): @bittersweetryan, @bradcliffe, @calumbrodie, @duncanbeevers, @hlvnst, @jonschlinkert, @Krutius, @samselikoff, @utkarshkukreti, @zeppelin

## License

(The MIT License)

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
