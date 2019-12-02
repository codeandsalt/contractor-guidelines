# Check your code style settings before committing.

Usually you can set them to a preset and it should work, as we should be using something that is fairly standard.

As a rule, though, unless your goal is to perform a mass-change in the code formatting (e.g. updating from PSR-1 to PSR-2) then **committing code which changes the formatting of unrelated items will be considered a bug.**

# Keep business logic/application functionality separate

Going hand-in-hand with testability, controllers are windows into the logic of the application. Since we want the application to best testable, this means that business logic or application functionality should be abstracted from things like:

* Controllers
* Artisan Commands

These classes should wrap functionality which can either be a part of the Model class (if the functionality is minimal, such as formatting data or grouping Eloquent queries, etc.)

If the functionality does a number of things, a Service class can be utilized to receive the information necessary to perform the operation and then call out to other services to handle the processing of the data.

Here are some examples:

* If you're creating a new object from a request, create a static wrapper method which takes the specific request and grabs the data from it.
* Let's say you need to send a notification. The notification should accept the minimum amount of data needed to process the request and a wrapper function can take Models and then wrap the creation of the Notification itself.
* You're uploading a file. You can create a Service which handles the creation and update of the related Model and throw any Exceptions that might occur. The only logic that would make it into the controller would be error handling and sending a response.
* If you have a private method on the controller that isn't used anywhere else, add it to a Helper class.

In general, you should be able to write tests for the majority of what you are doing without ever having to write a functional test. The only thing a functional test should generally look for is to make sure that response values are correct and shouldn't be testing business functionality.
