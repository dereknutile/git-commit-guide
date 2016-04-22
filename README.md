# Elegant Git Commit Guide

This is a living document created to help guide the delicate, often tedious process, of writing commit messages with the goal of establishing a convention for Git commits to ultimately produce legible, searchable, quality Git logs.

## Why?
Git is a collaborative tool, and being such, it is also a communication tool meant to describe the many details of development using clear and succinct messages.  In truth, the commit message is of little consequence unless the message needs to be reviewed.  At that point, if no convention has been followed, the message has a good chance of leaving out important, searchable, historic information.  The following guidelines attempts to formulate a structure that will deliver a more explicable message.


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
The {area} portion of the message is required, but more freeform.  The convention should be the area is single word in singular form like `test` rather than `tests`, and shortened if it makes sense: so `doc` or `config` may make sense, but `ftr` may be too obscure and in this case the suggestion would be the full word `feature`.

##### Message Convention
To write great Git commit messages, follow the following rules:

  * Separate the subject from the description with a blank line
  * Keep the message short with a goal of 50 characters or less
  * Use the extended description to describe the details (the what and why)
  * Start with an imperative verb - add, not adds or added
  * Character cases and punctuation are secondary to subject length

#### Examples of Well Formed Git Commit subjects

    new/doc - create standard README.md file
    edit/doc - add conventions section to README.md
    new/feature - setup gulp, bower, and sass
    edit/config - change bower asset directory
    new/style - setup and generate css from sass

... which looks like this in the Git log ...

    $ git log --oneline
    e1071be new/style - setup and generate css from sass
    c2da944 edit/config - change bower asset directory
    379623f new/feature - setup gulp, bower, and sass
    5319fa3 edit/doc - add conventions section to README.md
    65ae684 new/doc - create standard README.md file

### Git Commit Description
