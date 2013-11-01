# Do I Really Need jQuery?
#### Elijah Manor, Wed 2-3

### When Should I use jQuery?
- Do you need a quick prototype or proof of concept?
- Do you use jQuery plugins?
- Do you use a library or framework that depends on it?
- Do any of your browsers not cut it?

### But jQuery is too big (or too small)!
- As of jQuery 1.8 You can create custom builds -- pull from GitHub etc
- If it's a pain to do it from git, can also use jQuery Builder.

### Alternative Libraries
- Zepto.js: gzipped and largely jQuery compatible API; Doesn't support IE 6-10
- Min.js - very minimalistic and jQuery-like API; 60 lines of code with comments. Recommended

### Feature-by-feature comparison in IE9+: jQuery vs. Native
- Changing the HTML: Trivial in both
- Selectors: Native has a little bit less forgiving syntax, but it's pretty doable.
- Height and width: Very difficult; tons of jQuery code to unify the various native methods
- Bind and unbind: Wordier in native but not bad
- Delegate and Undelegate: Use a selector, call `.addEventListener()`, simple. 
- Also fairly similar: Target & Which, Stop, Proxy
- DOM.ready(): Easy, just put `<script>` at the end of `<body>` if you don't need to add scripts in other places. 
- Data (jQuery method):  

In general: Considerably easier to pull off in modern browsers, with a lot more constraints for older IE support.

Resources: http://manor.im/jq-free-js
http://manor.im/fixing-common-javascript-bugs