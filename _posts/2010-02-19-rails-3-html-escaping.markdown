---
  layout: post
  title: "Rails 3: HTML Escaping"
---

Well I cocked this one up in a lightning talk I attempted to give by mixing up methods in the powerpoint, so figured I owe it to post something that makes a little more sense..

### Rails 2
So you've been working on Rails apps for a while, and like all good developers, you've been escaping any content rendered in your views that your application's users might have entered, right?

eg. like this:

     <%= h some_string %>

### Rails 3
Now in Rails 3, all strings are html escaped automatically, so:

    <%= h some_string %>
    is now
    <%= some_string %>

No string by default is considered safe to render, and subsequently are HTML escaped. If you need to render html without it being escaped you need to effectively whitelist it as safe to render. This is done via `.html_safe`

    <%= some_string.html_safe %>


For a more detailed explanation, checkout:
http://yehudakatz.com/2010/02/01/safebuffers-and-rails-3-0/