# Check your code style settings before committing.

Usually you can set them to a preset and it should work, as we should be using something that is fairly standard.

As a rule, though, unless your goal is to perform a mass-change in the code formatting (e.g. updating from PSR-1 to PSR-2) then **committing code which changes the formatting of unrelated items will be considered a bug.**

Here are some particular rules that we enforce:

## If statements should always include curly brackets

    // Wrong.
    if (something === true) return 'a';
    
    // Also wrong.
    if (something === true)
        return 'b';
        
    // Correct.
    if (something === true) {
        return 'c';
    }

## Use guard clauses and simplify your if/then/else logic.

Lots of `if () {}` statements can really stack up and make everything hard to read. Consider this:

    function determineIfUserMeetsCriteria() {
        if (userIsLoggedIn === true) {
            if (userHasSomeSomeAttribute) {
                if (userHasAnotherParticularAttribute) {
                    return true;
                }   
            }
            else if (userHasAnotherAttribute) {
                return true;
            }
        }
        
        return false;
    }
    
In this case above, we can greatly simplify the readability.

    function determineIfUserMeetsCriteria() {
        // Guard #1.
        if (userIsLoggedIn !== true) {
            return false;
        }
       
        // Rework logic #2. 
        if ((userHasSomeSomeAttribute && userHasAnotherParticularAttribute)
            || userHasAnotherAttribute) {
            return true;
        }
        
        return false;
    }

In #1, we see the guard clause actually simplifies the reading of the code. If the user is not logged in, we'll always return false. In #2, the `if/else if` structure can be simplified. Often your IDE can do this for you.

The above is a contrived example, but it shows what the expectations are.

# Simplify return statements

    // This can be simplified...
    function foo(bar) {
        if (bar.baz === 'somevalue') {
            return true;
        }
        return false;
    }
    
    // To this...
    function foo(bar) {
        return bar.baz === 'somevalue';
    }

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

# Name your branches appropriately

On our projects, each branch should follow this pattern:

    CODE-ID-small-descriptive-phrase
    
For example, if you are working ticket PROJ-5 and that task is writing tests for an authentication system, you might name the branch:

    PROJ-5-auth-system-tests

