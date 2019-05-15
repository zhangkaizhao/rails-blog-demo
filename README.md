# A blog demo: getting started with Rails

via https://www.yuque.com/ruby-china/rails-guides/source-zh-cn-getting-started (in Chinese)

## Development steps

### Setup Ruby and Rails

* Get Ruby 2.6.2 installed, e.g. via ruby-install/chruby in Linux
* Get Rails 5.2.2 installed, via `gem install rails`

### Create blog application and install dependencies

```sh
rails new blog
cd blog
bundle install
```

Note: Before running `bundle install`, change the line

```ruby
gem 'sqlite3'
```

to

```ruby
gem 'sqlite3', '~> 1.3.6'
```

in `Gemfile` file due to an issue of sqlite3 gem version dependency.

### Run the development server

```sh
bundle exec ./bin/rails server
```

If there is no other Ruby gems installed with this Ruby installation, we can run without bundle, e.g.

```sh
./bin/rails server
```

### Create a Welcome controller and its index action for application home page

* Generate Welcome controller and its index action
* Edit view of Welcome controller's index action with some HTML code to show "Hello, Rails!"
* Configure routes for application home page, set `root` to Welcome controller's index action

### Create articles resources

* Add articles resources to routes

* Generate Articles controller

* Add new action to Articles controller to show a form for creating new article
* Add view of Articles controller's new action with a form

* Add create action to Articles controller for saving data from form

* Generate Article model
* Run databse migration to create database table for Article model

* Edit create action of Articles controller to save new article and then redirect to article page
* Move code of getting data from form to private to avoid security issues (a.k.a strong parameters)

* Add show action to Articles controller for article page
* Create view for Articles controller's show action

* Add index action to Articles controller for listing each article
* Edit view of Articles controller's index action

* Add link to articles resources in application home page which is view of Welcome controller's index action
* Add link to view of new action of Articles controller in view of index action of Articles controller
* Add link to view of index action of Articles controller in view of new action of Articles controller
* Add link to view of index action of Articles controller in view of show action of Articles controller

* Add validations to Article model
* Update new action and create action of Articles controller for validation failure condition
* Update view of new action of Articles controller to show error messages

* Add edit action to Articles controller for showing update form
* Add view of Articles controller's edit action
* Add update action to Articles controller for saving updated article from form
* Add link to view of edit action of Articles controller in view of index action of Articles controller
* Add link to view of edit action of Articles controller in view of show action of Articles controller

* Refactor forms in views of new action and edit action of Articles controller by using partial views

* Add destroy action to Articles controller for deleting article
* Add link to destroy action of Articles controller in view of index action of Articles controller

### Create comments resources

* Generate Comment model with references to Article model
* Run databse migration to create database table for Comment model

* Edit Article model to add relationship with Comment model

* Add comments resources to routes

* Generate Comments controller
* Edit view of show action of Comments controller for showing new comment form
* Add create action of Comments controller to saving new comment from form
* Edit view of show action of Comments controller for showing added comments

* Refactor new comment form in view of show action of Articles controller by using partial views
* Refactor comments in view of show action of Articles controller by using partial views

* Add link to destroy action of Comments controller in partial view of comment
* Add destroy action to Comments controller for deleting comment

* Update Article model to delete related comments when deleting article

### Add authentication for security

* Add HTTP Basic Authentication to Articles controller
* Add HTTP Basic Authentication to Comments controller

## More

The source of this document is https://ruby-china.github.io/rails-guides/getting_started.html (in Chinese).
And it is also a Chinese translation of Rails Guides.
