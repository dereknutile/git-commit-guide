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
So, like the Git manual suggests, we should keep our subjects to ~50 characters or less.  In addition, we should strive to add a few minor attributes to each message so on quick glance, our reviewer can assess the true nature of the commit.  To do this, we follow a Git commit message convention of:

    {category}/{area} - {message}

##### Category Convention
The {category} portion of the message should fall under one of the following types:

  * `new` Representing the addition of something new to the repository.
  * `edit` Is a refactor of something that previously existed in the repository.  And edit could include code changes or a file deletion for example.
  * `fix` Is a specific type of edit or refactor where a specific bug fix has been introduced.

##### Area Convention
The {area} portion of the message is required, but allows for more freeform.  The convention for the {area} is to use a single word in singular form like `test` rather than `tests`, and shortened if it has common usage like `doc` or `config`.  Here are some common areas:

  * `{feature}` is a specific function or attribute of the project like `login`, `blog`, or `api`.
  * `style` could be a generic tag for css, scss, sass, etc.
  * `format` when manipulating document format like changing tabs to spaces.
  * `doc` is used for documentation, readme, commenting, or instructions.
  * `test` is test code.

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

    new/doc - Create standard README.md file
    edit/doc - Add conventions section to README.md
    new/feature - Setup gulp, bower, and sass
    edit/config - Change bower asset directory
    new/style - Setup and generate css from sass

... which looks like this in the Git log ...

    $ git log --oneline
    e1071be new/style - Setup and generate css from sass
    c2da944 edit/config - Change bower asset directory
    379623f new/feature - Setup gulp, bower, and sass
    5319fa3 edit/doc - Add conventions section to README.md
    65ae684 new/doc - Create standard README.md file

### Git Commit Description
The Git commit description expands the detail of the subject.  Try to adhere to the following rules:

  * Use the Git commit description to explain `what` was committed not why it was or how it was.
  * There is no character limit for the description.
  * Use the description to note specific details addressed bug fixes.
