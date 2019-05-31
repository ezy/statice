---
title: Angular $http get from the console
url: 674.html
id: 674
comments: false
categories:
  - Code
date: 2015-09-03 13:48:26
tags:
---

Super useful string of code for calling http get requests directly from the console in Chrome:

    $http = angular.element(document.body).injector().get('$http');

then

    $http.get(...) // or post or whatever
    

Then test as many API request as you like.