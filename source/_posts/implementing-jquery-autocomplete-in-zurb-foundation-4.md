---
title: Implementing Jquery Autocomplete in Zurb Foundation 4
url: 424.html
id: 424
comments: false
categories:
  - Code
date: 2013-05-15 11:37:13
tags:
---

[Zurb Foundation](http://foundation.zurb.com/docs/) 4 (4.1.6 as of this post to be specific) is a fantastic non-opinionated framework that is reasonably vanilla out of the box and contains a tonne of brilliant functionality. If you've used it already - you know the awesome. ![Zurb](http://c1940652.r52.cf0.rackcdn.com/514b5e31fb4f442f530004e1/Screen-Shot-2013-03-21-at-12.22.52-PM.png)   One of the quirks I came up against when using the framework for prototyping was around the jquery autocomplete functionality so I wanted to get it down for posterity. (Hit the post title to read on) 

### 1\. Head code

Implement all the jquery in the head code. `<!DOCTYPE html> ... <script src="js/vendor/custom.modernizr.js"></script> <!-- Jquery UI stuff --> <link rel="stylesheet" href="http://code.jquery.com/ui/1.10.3/themes/smoothness/jquery-ui.css" /> <script src="http://code.jquery.com/jquery-1.9.1.js"></script> <script src="http://code.jquery.com/ui/1.10.3/jquery-ui.js"></script> <script> $(function() { var availableTags = [ "ActionScript", "AppleScript", "Asp", "BASIC", "C", "C++", "Clojure", "COBOL", "ColdFusion", "Erlang", "Fortran", "Groovy", "Haskell", "Java", "JavaScript", "Lisp", "Perl", "PHP", "Python", "Ruby", "Scala", "Scheme" ]; $( "#tags" ).autocomplete({ source: availableTags }); }); </script> </head>`

### 2\. Body

Make sure you have the right id and class variables in the body code. `<body> <div class="row"> <form class="custom"> <fieldset> <legend>Fieldset</legend> <div class="row"> **<div class="large-12 columns ui-widget">** **<label for="tags">Input Label</label>** **<input id="tags" type="text" placeholder="large-12.columns">** </div> </div> ...`

### 3\. Javascript scripts before the /body

Make sure that the correct JS is doing what it should and is being called last just before the /body end tag, otherwise nothing will work properly (duh): `**<script>** **document.write('<script src=' +** **('__proto__' in {} ? 'js/vendor/zepto' : 'js/vendor/jquery') +** **'.js><\/script>')** **</script>** <script src="js/foundation.min.js"></script> <!-- <script src="js/foundation/foundation.js"></script> <script src="js/foundation/foundation.alerts.js"></script> <script src="js/foundation/foundation.clearing.js"></script> <script src="js/foundation/foundation.cookie.js"></script> <script src="js/foundation/foundation.dropdown.js"></script> <script src="js/foundation/foundation.forms.js"></script> <script src="js/foundation/foundation.joyride.js"></script> <script src="js/foundation/foundation.magellan.js"></script> <script src="js/foundation/foundation.orbit.js"></script> <script src="js/foundation/foundation.placeholder.js"></script> <script src="js/foundation/foundation.reveal.js"></script> <script src="js/foundation/foundation.section.js"></script> <script src="js/foundation/foundation.tooltips.js"></script> <script src="js/foundation/foundation.topbar.js"></script> --> <script> $(document).foundation(); </script> </body> </html>` And that should be it. The last thing to check is that your folder structure for CSS and JS are correct. And remember that the Proto.js and Jquery.js fallback script is absolutely key. Also that the foundation.min.js contains the Jquery library itself.