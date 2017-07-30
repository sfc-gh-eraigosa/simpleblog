# simple blog exercise

This is an exercise project for learning how to create a RAILS MVC app.
Based on video tutorial given from [Traversy Media - article](https://www.youtube.com/watch?v=pPy0GQJLZUM).

# Developer Notes

## Create Initial app and controller
1. create simpleblog app
   ```
     rails new simpleblog
     cd simpleblog
     bundle install
     rails-server
   ```
   Check site http://localhost:3000

1. Create Posts controller
   ```
   rails g controller Posts
   ```

1. Create controller `index` function in `app/controller/posts_controller.rb`

1. Create view for `index` controller in `app/views/posts/index.html.erb`

1. Add route for `index` to `config/routes.rb` and test http://localhost:3000 again.

## Create Pages Controller

1. Add `Pages` controller
   ```
   rails g controller Pages
   ```

1. Create `about` controller function in `app/controllers/pages_controller.rb`

1. Create `About` `Pages` view in `app/views/pages/about.html.erb`

1. Add route to `config/routes.rb` for about GET method, check http://localhost:3000/about

1. Update `About` to use `@title` controller attribute with `About US` text and erb output in `About` view, test http://localhost:3000/about again.  Do the same for `@content`.

## Handle Posts resources

1. Add `resources :posts` to `config/routes.rb` check `rails routes` to verify new posts routes exist.

1. Create `new` method in `Posts` controller, `app/controllers/posts_controller.rb`

1. Create `new` view in `app/views/posts/new.html.erb` and test it http://localhost:3000/posts/new

1. Create `form_for` on `new.html.erb`, tip http://guides.rubyonrails.org/form_helpers.html#using-form-helpers  and https://apidock.com/rails/ActionView/Helpers/FormOptionsHelper

1. Create controller `create` method in `app/controllers/posts_controller.rb`

1. Create `Post` model
   ```
   rails g model Post title:string body:text
   rails db:migrate
   ```

1. Create `show` method in `posts_controller.rb` and `show.html.erb` View that corresponds to it. Test http://localhost:3000/posts/new

1. Setup `index` for Posts controler to show all posts.  Update `index.html.erb` to show all posts.

## Update styles to bootstrap

1. Add bootstrap css : https://www.bootstrapcdn.com/alpha/
    Update `views/layouts/application.html.erb` with url to CSS link.

1. Get starter template http://getbootstrap.com/examples/starter-template/

1. Update `home` routes

1. add `form-control` class to f.text.. fields on `new` form view.

## Add Post Create Form Validation

1. Add form validation with model file for `Post`

1. On `create` method of `Posts` controller add validation check

1. Add error message for form input validation on `new.html.erb` View and update `new` method `@post` attribute for controller

## Navigate and Edit Posts

1. Each post should have a navigation in `views/posts/index.html.erb`
   ```
   <%= link_to "Read More", post_path(post), :class => 'btn btn-default' %>
   ```

1. Add edit link to `show` View in `view/posts/show.html.erb`

1. Add `edit` method in `Posts` Controller.

1. Create `edit.html.erb` View to edit the post, copy `new.html.erb` and edit the page.

1. Add `update` method to controller.

## Delete Posts

1. Add `destroy` method to `Posts` controller.

1. Add `delete` link to the `show` view in `views/posts/show.html.erb`

## Add Comment functionality
