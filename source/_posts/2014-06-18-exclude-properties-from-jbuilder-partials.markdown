---
layout: post
title: "Exclude properties from JBuilder partials"
date: 2014-06-18 15:04:23 -0400
comments: true
categories:
- ruby
- open-source
- software
---
I found the lack of documentation for JBuilder partials to be very frustrating. Ideally I could write one partial for each of my ActiveRecord models and re-use them in all my JBuilder views. The problem comes when you have a model like User, for example, which has one or more Photos. When I request the `show` action for my User controller, I want the User partial to be rendered with it's Photo as a child (using the Photo partial). On the other hand, when I request the `show` action for my Photo, I want the Photo partial to be rendered with it's User as a child (using the User partial). This can lead to an infinite loop which, at first glance, can only be solved by making many individual partials for the same model, like `photo_without_user` and `photo_with_user`.<!-- more -->

Going a little deeper, you'll find that the `partial!` method will pass any data you give it along to the view (the unrecognized hash keys will be available to the view as local variables of the same name). In the following example, I simply pass a custom variable, `exclude`, into the call to `partial!` and use it as a condition in the photo partial view. Obviously this will grow cumbersome if you are nesting partials more than a couple layers deep, but for my use, it works quite well.

    # In `users/_user.json.jbuilder`:
    json.(user, :id, :name)
    json.photo do
      json.partial! 'photos/photo', photo: user.photo, exclude: [:user]
    end

...

    # In `photos/_photo.json.jbuilder`:
    json.(photo, :url, :caption)
    unless exclude.include?(:user)
      json.user do
        json.partial! 'users/user', user: photo.user
      end
    end