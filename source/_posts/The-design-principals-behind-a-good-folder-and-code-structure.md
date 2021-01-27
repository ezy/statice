---
title: The design principals behind a good folder and code structure
date: 2020-02-11 07:59:53
tags:
---
 
Good design is always human centred. As developers we are the shepherds of bytes and pixels, binary and exacting, but we are still messy humans. There's a great saying that "development is the art of introducing bugs to a blank file". And it's true that all the problems we encounter in the development cycle are because of people. Someone somewhere in the libraries and code delivered functionality that was imperfect for our current situation. Therefore taking a human centered approach to the many and varied design patterns in the stack of development is a key to continued harmony of team and work cycle. Because the goal is to have a maintainable (scalable) code base with good test coverage that is stable and not tightly coupled (it can be split into smaller chunks easily).
 
So let's start with describing the only code structure that is right for all teams. The right code structure is the one that makes your team the most productive first. And second, follows any well established patterns and conventions in the existing code base.
 
## Folders
 
Any new team in a green fields project without a defined architecture (almost everyone IME) will take a bit of time to gel their patterns. And this will depend on the background and preferences of your developers. But a great starting point is to use tried and true patterns that the majority of developers should recognise:
 
Services
Factories
Maps
Controllers
Models/Types
Views
 
 
## File naming
 
When naming files the format is less important than the description. File names are for humans first, and should be descriptive enough to get a clear picture of what to expect from the methods within.
 
## Methods
 
Distinct reusable methods (objects/functions) that can be unit tested with clear input and output bring stability and confidence refactoring. Targeting data patterns or events are both good approaches related to structuring methods. Things to avoid are assuming that everyone thinks the same way as you, and being inflexible in your approach to structutring code. Following existing patterns in the code base, no matter how foreign will ultimately make you a better developer.
 
## Conclusion
 
The result of a well defined structure is a testable, maintanable, scabale code base.