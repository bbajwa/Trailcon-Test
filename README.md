# Trailcon-Test Notes

**Please read the instructions.**

Using Codeigniter, try to complete the following tasks. Parts One and Two are mandatory. Part Three is not, but nice to have.

Before starting, create a github repository to track your work. You will be using that repository to share your code with us.

Download Codeigniter and create a `Hello, world!` on your own development environment. Depending on your environment, this may not be trivial; but hopefully it is not very difficult. 
Google is always your friend. But it is important for developers to be able to set up and maintain development environments.

After completing each part of this test, ensure that there is a branch in your git repository that holds a complete version of that part. For example, after completing Part One, you might have the following branches

    Part1
    master

You have discretion over how you would like to organize and name these branches - just **make sure that it is easy for us to view a completed and *mostly* bug-free version of Parts One and Two**, whether or not you start or complete Part Three. For this reason, it is completely acceptable to submit a partially-completed Part Three.

It is OK to use `Plain-Old-PHP` in the view. If you prefer to use Twig or Smarty or some other templating engine, that is great, but not necessary.

Please submit your test by updating your github repository and sending us a link.

## Part One

Create a Codeigniter site. In the homepage, perform `TrailconLeasing`. Instructions:

Print out 100 lines. If the line number is divisible by 3, print out 'Trailcon'. If the line number is divisible by 5, print out 'Leasing'. If it is divisible by both, print out 'TrailconLeasing'. If none of previous conditions are met, print out the number. E.g.:

    1
    2
    Trailcon
    4
    Leasing

(line 15 has `TrailconLeasing`), and so on to 100.

Notes:

- No logic goes in the view, only a loop. This may be accomplished by performing the operation in the Controller, then passing an array to the view.
- Presentation style doesn't matter at all. The only thing that matters is that the html is valid and that there is a doctype.
- The actual TrailconLeasing implementation should only take about ten minutes. Perhaps it will take a little more time to set up Codeigniter, and to write out your Controller and View.

## Part Two

Create a page named `contest` that lists the following fields:

    First Name
    Email Address

On it list every row of a database table. The database table should have those two fields (as `firstname` and `email`), and perhaps any other fields that a web application database table is likely to have.

Add a `Create` link, and for every item in the list, add an `Edit` link.

Create should go to

    contest/details

Edit should go to

    contest/details/<UNIQUE_IDENTIFIER>
    e.g.
    contest/details/12

In the details page, make an edit form that edits firstname and lastname.

The application must interface with the **MySQL** database through Codeigniter Models. Field validation must also be done with the ORM. Use the following validation:

    firstname: not empty
    email: unique, not empty, valid email address

Show messages for invalid input. Just use the messages that the ORM's validation provides.

Notes:

- The view should only have basic *presentation-related* logic. There probably will be a loop and a few conditions that decide whether to display a message or invalid input, etc.
- Please include a dump of your MySQL table schema so that it's easy for us to user-test this part.

## Part Three (OPTIONAL)

Using Codeigniter, make a French version of the site. The french version of `contest` should be called `concours`.

Translate the following labels as:

    firstname, label: 'Prénom'
    email, label: 'Adresse e-mail'

Any other French text is not necessary. You can just keep them as English or use whatever you like. It is enough that you can show that you are *able to* use the framework's internationalization.

For URLs use language prefixes. Acceptable URLs are:

    mysite.com/en/
    mysite.com/fr/
    mysite.com/en/contest
    mysite.com/fr/concours
    mysite.com/en/contest/entry
    mysite.com/fr/concours/entree

Notes:

- You should **not** have to add new Controllers or Actions for this Part. A proper internationalization should just display different text for the same controller/actions and the same views as before.
