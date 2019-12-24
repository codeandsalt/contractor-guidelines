# Contractor Guidelines

This document provides a list of best practices and concepts for contractors.

You should also review these:

* [Coding Guidelines](coding-guidelines.md)
* [Data Protection Policy](data-protection-policy)

At a high level, it's important to remember that there are two sides to a freelance/contract relationship. One side is the contractor and the other, of course, the one hiring.

In our relationships, we desire to assume the best from those we hire and as such you must know that each and every person matters to us. Yes, we talk in hours and tasks, but we take into considering the desire/need to work from you and factor that into how we plan and operate. Likewise, while we, as the contracting business, have final say over matters, we want you to input your thoughts and ideas into not only the work you do, but also into how we do things.

With that in mind, here are some things we expect from you.

# You are responsible for getting what you need.

This should be a given, but when you are given a task, it is possible that the task did not happen to include everything you needed. Maybe it needs designs. Perhaps the architecture is spotty or missing some details. Sometimes JIRA doesn't save our comments. Whatever the case may be, if there is *any* confusion about something or you are uncomfortable implementing something, **ask!**

There are *no* dumb questions! Please ask us if anything doesn't look right or you don't know how to start working on something.

# Build according to the standards of the project.

Every framework that we use has coding standards. And many times, these frameworks have methods for doing things which are possibly unique to their ways. Sometimes doing things the "right way" takes time and effort. We are fine with you doing things the right way and will never fault you for spending a little more time to make it right.

That said, if a deadline or some other reason comes along which might cause you to not be able to do that, then you should raise a Technical Debt concern so that it can be addressed later. The code we deliver to the client is a reflection of our values and our competencies.

# Implement the designs in light of approved styles.

 If there is a design which comes along and you find that it doesn't map to approved styles, you should err toward approved styles. For example, if you receive a design where a "Heading 2" is normally used but the font doesn't quite match, then you should use Heading 2. If you find yourself doing this often, please let us know—generally this is just a minor oversight but shouldn't be happening.

# Don't commit anything unrelated to what you are working on.

It can be really tempting to fix a bug in a feature branch you are working on. Or sometimes, you might be working on a file and the formatting is off, so you fix it. Please, please do not do this. Doing this can cause issues down the road with mass updates or the bug being committed in another branch.

Our goal is to review 100% of commits before they are merged in. Making those review diffs as small as possible really helps in this endeavor and works to eliminate conflicts later on down the line.

Do: before you commit, review what you are committing. Using a tool like SourceTree or running `git commit -p` can give you terrific insights into what you are committing and help you make sure you're not committing anything accidentally.

# Commit Messages should follow a pattern

Commit messages describes should always start with the ticket ID:

```
TICKET-#### - A summary of the changes.

Details about what was done.
Added FooController.
Updated BarService.
Changed style for BazComponent.
```

Commit messages should describe what the commit does. If a single line does not suffice, then you should use additional lines after the first line to describe what changes were made and why. Every commit message should start with the ticket number.

Additionally, a commit message is also an OK place to add notes about what you are doing. In general, if you're changing calling conventions or deprecating something, the code and tickets should also reflect those notes as well. But for code reviews, you might want to put some information in there about what you are doing and why:

* Why are you reverting this change?
* Is there a particular hack that might be important for others to know about?

## Resources:

* [How to Write a Git Commit Message](https://chris.beams.io/posts/git-commit/)


# Communicate your availability or lack thereof.

If you have an emergency, need a break, or you have more time, please let us know. We plan things based on what we know and if that changes, then we can run into big problems!

# Report your time accurately and honestly.

If it takes you 5 hours to do something which should have taken 30 minutes, we want to know. There are times when these things happen: you had to re-import a large DB for testing or you were having problems getting a build process to work. There are times when you may even want to not-bill for something because you realized you spent too much time on it. We still want to know how much time you did spend on it, as it gives us insight into our tooling and processes and we can work to eliminate that stuff in the future.

# Build tests.

If you're adding code, build new tests.
If you're changing code, change existing tests.
If you're fixing a bug and the tests are passing, write tests to make the bug fail, and then fix the bug.

# Run test suites before committing.

This will save you a lot of time. Just run the test suites before committing. If you find a bug outside of what you are doing, you can fix that bug if it causes the build to fail, but please communicate that first.
