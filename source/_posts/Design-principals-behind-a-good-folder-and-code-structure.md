---
title: Design principals behind good folder and code structure
date: 2020-02-10 19:19:14
tags:
  - code
  - design
  - javascript
---

Good design is always human centered. As developers we are the shepherds of bytes and pixels, binary and exacting, but we are still messy humans. There's a great saying that "development is the art of introducing bugs to a blank file". And it's true that all the problems we encounter in the development cycle are because of people. Someone somewhere in the libraries and code delivered functionality that was imperfect for our current situation. Therefore taking a human centered approach to the many and varied design patterns in the stack of development is a key to continued harmony of team and work cycle. Because the goal, is to have a maintainable (scalable) code base (with good test coverage) that is stable and not tightly coupled (it can be split into smaller chunks easily).

So let's start with describing the only code structure that is right for all teams. The right code structure is the one that makes your team the most productive first. And second, follows any well established patterns and conventions in the existing code base.

## Folders

Any new team in a green fields project without a defined architecture (almost everyone IME) will take a bit of time to gel their patterns. And this will depend on the background and preferences of your developers. But a great starting point is to use tried and true patterns that the majority of developers should recognise loosely defined as follows:

**Services (similar to factories):** A constructor for reusable business logic that can be imported across the application to provide a group of methods for common use cases.

**Factories (similar to services):** Similar to a service but typically returns an object for a specific use case or set of business rule.

**Maps/Constants:** Fixed properties that persist data state.

**Controllers:** Core business logic for each module.

**Models/Types:** Describe data structures and used for validating incoming and outgoing data.

## File naming

When naming files, the format is less important than the description. File names are for humans first, and should be descriptive enough to get a clear picture of what to expect from the methods within. From there, whatever convention has been implemented - stick with it as consistency is key. My favorite format is lowercase with hyphens, including the file type: search

- file-name-description.map.js
- file-name-description.types.js
- file-name-description.controller.js
- file-name-description.controller.test.js

## Methods

Distinct reusable methods (objects/functions) that can be unit tested with clear input and output bring stability and confidence refactoring. Targeting data patterns or events are both good approaches related to structuring methods. Things to avoid are assuming that everyone thinks the same way as you, and being inflexible in your approach to structuring code. Following existing patterns in the code base, no matter how foreign will ultimately make you a better developer. Be as descriptive as possible in your naming convention:

- `const save = (f) => {}` bad
- `const saveFile = (data) => {}` good
- `const saveFileInPDFFormat = (fileData) => {}` best
- `const saveFileForExportConvertHTMLToPDFFormat = (inputFileData) => {}` ridiculous but better than bad

## Conclusion

Humans are the benefactor when it comes to good folder and file design. Remember that code that you wrote 2 weeks ago is code that you're seeing for the first time. So you'll be the ultimate benefactor of your own good practice. Always be flexible in your approach, and defer to the team conventions as long as they're widely accepted internally and externally. The result of a well defined structure is a testable, maintainable, scalable code base. Which makes for happy developers, and enjoyable work.
