# Rails Application template

Open source base template for rails, get your new rails project up and running quickly. This is the bare minimum which I feel is enough to kickstart your rails project running rspec and....

####Sqlite3

`rails new -T`

####Postgres

`rails new -T -d=postgresql`

## Setting Up

Delete the gems you do not need and uncomment the ones you need.

### Front-end dependecies
- [Title](https://github.com/calebthompson/title)
- [bootstrap-sass](https://github.com/twbs/bootstrap-sass)
- [FFaker](https://github.com/ffaker/ffaker)

Run `rake tmp:clear` to clear your cache before auto prefixer will take effect


### Using SCSS dependencies

```
# Remember to rename your application.css to application.scss
# app/assets/stylesheets/application.scss

# Bootrap sass
@import "bootstrap-sprockets";
@import "bootstrap";

# Bourbon/Neat
@import "bourbon";
// Overriding default neat grid
// @import "grid-settings";
@import "neat";

# Foundation
rails g foundation:install

@import "foundation_and_overrides";

# Normalization if your framework doesn't provide
@import "normalize-rails"
```

### Javascript

```
//= require jquery
//= require jquery_ujs
//= require turbolinks
//= require_tree .

# Bootstrap
//= require bootstrap-sprockets

```

### Development Dependenies

- Using [Bullet](https://github.com/flyerhzm/bullet) is optional

#### Registrations
- Devise
- OmniAuth
```
$ rails generate devise:install
$ rails generate devise MODEL eg. MODEL => User
```


### Test Depencies

Generate the folders and config for rspec and

```
$ rails generate rspec:install

# If you install webmock and rspec
# spec/spec_helper
require 'webmock/rspec'

# Add this line into your spec/rails_helper

Shoulda::Matchers.configure do |config|
  config.integrate do |with|
    # Choose a test framework:
    with.test_framework :rspec
    with.library :rails
  end
end
```

If using *rspec-rails* and *devise*, add this into `spec/rails-helper` config to allow commands like current_user and sign_in

```
RSpec.configure do |config|
  config.include Devise::TestHelpers, type: :controller
  config.include FactoryGirl::Syntax::Methods
end
```

## Contributing

1. Clone the repo
2. Create a branch `fork/<some_br>`
3. Add stuff and create a pull request
4. ...
5. PROFIT!
