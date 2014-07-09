Rethinking ngController
========================

A better way to decouple controller and model. It's a good practice to free the controller from any data. Based on http://toddmotto.com/rethinking-angular-js-controllers/ with few syntax changes.

=====
Important Notes
=====


* Factories hold the Model, change, get, update, and persist the Model changes
* Controllers should hold zero logic
* Controllers should bind references to Models only (and call methods returned from promises)
* Controllers only bring logic together
* Controller drives Model changes, and View changes. Keyword; drives, not creates/persists, it triggers them!
* Delegate updating of logic inside Factories, don't resolve data inside a Controller, only update the Controller's value with updated Factory logic, this avoids repeated code across Controllers as well as Factory tests made easier
* Use "Controller as"
* Keep method/prop names consistent across shared methods, such as this.something = MyFactory.something; otherwise it becomes confusing
* Factories hold the Model, change, get, update, and persist the Model changes
* Think about the Factory as an Object that you need to persist, rather than persisting inside a Controller
* Talk to other Factories inside your Factory, keep them out the Controller (things like success/error handling)
* Try to avoid injecting $scope into Controllers, generally there are better ways to do what you need, such as avoiding $scope.$watch()
