# Elegant Git Commit Guide

This is a living document created to help guide the delicate, often tedious process, of writing commit messages with the goal of establishing a convention for Git commits to ultimately produce legible, searchable, quality Git logs.

## Why?
Git is a collaborative tool, and being such, it is also a communication tool meant to describe the many details of development using clear and succinct messages.  In truth, the commit message is of little consequence unless the message needs to be reviewed.  At that point, if no convention has been followed, the message has a good chance of leaving out important, searchable, historic information.  The following guidelines attempts to formulate a structure that will deliver a more explicable message.

To summarize, good Git commit messages do the following:

  * To assist the project or development review.
  * To build documentation.
  * To help define release notes.

## Conventions
Git commit messages have two main parts - the **subject**, which is required, and an optional **description**.  The [Git manual](https://www.kernel.org/pub/software/scm/git/docs/git-commit.html#_discussion) states:  *Though not required, it’s a good idea to begin the commit message with a single short (less than 50 character) line summarizing the change, followed by a blank line and then a more thorough description.*

### Git Commit Subject
So, like the Git manual suggests, we should keep our subjects to ~50 characters or less.  In addition, we should strive to add a few minor attributes to each message so at a quick glance, our reviewer can assess the true nature of the commit or visually be able to filter out commit types.  To do this, we follow a Git commit message convention of:

    {action}/{feature} {message}

##### Action Convention
The {action} portion of the message should fall under one of the following types:

  * `n` - New: Representing the addition of something new to the repository.
  * `e` - Edit: Is a refactor of something that previously existed in the repository.  An edit could include code changes or a file deletion for example.
  * `r` - Remove: Calls out that a file or feature was removed from the repository.
  * `f` - Fix: Is a specific type of edit or refactor where a specific bug fix has been introduced.

##### Feature Convention
The {feature} portion of the message is required, but allows for more freeform.  The convention for the {feature} is to use a single word in singular form (think `test` not`tests`), and shortened if it has common usage like `auth` or `config`.  Here are some common features:

  * `auth`, `cart`, `doc`, and `api` all briefly describe a feature or element.  The key here is to use a short, singular word that describes the area of development.
  * `style` could be a generic tag for css, scss, sass, etc.
  * `format` when manipulating document format like changing tabs to spaces.
  * `*` for work that can't fall into a category.

Some teams will come up with their own conventions for the area.  Short is better as long as it's easy to understand.

##### Message Convention
To write great Git commit messages, follow the following rules:

  * Separate the subject from the description with a blank line
  * Keep the message short with a goal of 50 characters or less
  * Use the extended description to describe the details (the what and why)
  * Capitalize the first letter of the message
  * Leave out commas and periods
  * Start with an imperative verb - add, not adds or added
  * Always try to have the message complete this sentence: `This commit will {message}`.

#### Examples of Well Formed Git Commit subjects

    n/doc - Create standard README.md file
    e/doc - Add conventions section to README.md
    n/feature - Setup gulp, bower, and sass
    f/js - Fix missing brace in blah.js
    e/cfg - Change bower asset directory config
    n/style - Setup and generate css from sass

... which looks like this in the Git log ...

    $ git log --oneline
    e1071be n/doc - Create standard README.md file
    c2da944 e/doc - Add conventions section to README.md
    379623f n/feature - Setup gulp, bower, and sass
    488e30f f/js - Fix missing brace in blah.js
    5319fa3 e/cfg - Change bower asset directory config
    65ae684 n/style - Setup and generate css from sass

### Git Commit Description
The Git commit description expands the detail of the subject.  Try to adhere to the following rules:

  * Use the Git commit description to explain `what` was committed not why it was or how it was.
  * There is no character limit for the description.
  * Use the description to note specific details addressed bug fixes.
