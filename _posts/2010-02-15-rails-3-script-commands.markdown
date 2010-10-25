---
  layout: post
  title: "Rails 3: Script Commands"
---

One of the new changes introduced in Rails 3 is a rework of the rails script commands. Command-line scripts have been pushed into the railties gem and streamlined into a new, more generic `script/rails` command.

Previously (pre Rails 3), to do things like loading a console you would do the following:

    script/console

This has now changed to:

    script/rails console

The script command can actually be shortened to just `rails`, eg:

    rails console

And additionally, the most popular commands have shortcuts:

    rails c  # rails console

### List of Commands

Lifted straight from the `--help` option, this is a list of the commands available:

    generate     Generate new code (short-cut alias: "g")
    console      Start the Rails console (short-cut alias: "c")
    server       Start the Rails server (short-cut alias: "s")
    dbconsole    Start a console for the database specified in config/database.yml
                 (short-cut alias: "db")
    application  Generate the Rails application code
    destroy      Undo code generated with "generate"
    benchmarker  See how fast a piece of code runs
    profiler     Get profile information from a piece of code
    plugin       Install a plugin
    runner       Run a piece of code in the application environment

### Specific environments

Similar to the previous version of the script system, you can pass the environment as an additional argument, eg:

    script/rails console test
    RAILS_ENV=test script/rails console
