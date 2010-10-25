---
  layout: post
  title: "Rails 3: Deprecated Constants"
---

The following constants used in Rails have been deprecated in Rails 3:

    RAILS_ENV
    RAILS_DEFAULT_LOGGER
    RAILS_ROOT

Instead, you should start using the following:

    Rails.env
    Rails.logger
    Rails.root

These methods aren't new with Rails 3 but if you haven't been used them much, `Rails.env` and `Rails.root` have some additional features that are quite handy.

### `Rails.env`

Rails.env returns a string with the name of the environment Rails is loaded with:

    Rails.env
    #> "development"

Additionally, `Rails.env` is a String wrapped inside the `StringEnquirer` class found in `ActiveSupport`. This allows for easier checking of the Rails environment like so:

    # When the Rails environment is 'development'
    Rails.env.development?
    #> true
    
    Rails.env.production?
    #> false

    Rails.env.a_non_existing_environment?
    #> false

### `Rails.root`

Rails.root returns a `Pathname` object (Ruby Core). `Pathname` objects mix together the functionality of `File`, `FileTest`, along with bits of `Dir` and `FileUtils`, allowing to shortcut and not use methods like `File.join` but instead:

    Rails.root.join('app', 'controllers')
    #> #<Pathname:/Users/mark/workspaces/ruby/rails3_demo/app/controllers>

If you only want the path string simply call `to_s`

    Rails.root.join('app', 'controllers').to_s
    #> "/Users/mark/workspaces/ruby/rails3_demo/app/controllers"
