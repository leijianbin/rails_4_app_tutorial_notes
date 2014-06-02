Level 01 - A New App
-----------

#Overview
* We are making a new app called golp which will eventually run on Heroku
* The core of our app will be Things which are stored in a postgres database
* We will use rspec instead of test unit so we'll use the -T option to the ```rails new``` command
* We'll add our default set of development gems including


```
group :development do
	gem 'quiet_assets'
	gem 'better_errors'
end
```

Support for chrome rails panel plugin:

    group :development do
      gem 'meta_request' # https://chrome.google.com/webstore/detail/railspanel/gjpfobpafnhjhbajcjgccbbdofdckggg
    end

For pry / debugging fans:

    group :development do
      gem 'binding_of_caller' # Going up the stack  binding.of_caller(2).eval('var = :hello')
      gem 'awesome_print' # In the rails console: ap Account.limit(2).all
      gem 'pry-rails' # Uses pry instead of irb for the console
      gem 'pry-byebug'
    end

Install RSpec: read the attached stack overflow rspec article


	group :development, :test do
		gem 'rspec-rails'
	end


#Level Resources

* [Stack Overflow: Use-rspec-instead-of-test-unit](http://stackoverflow.com/questions/6728618/how-can-i-tell-rails-to-use-rspec-instead-of-test-unit-when-creating-a-new-rails)
* [quiet_assets](https://github.com/evrone/quiet_assets)
* [better_errors](https://github.com/charliesome/better_errors)
* [Rails Panel](https://chrome.google.com/webstore/detail/railspanel/gjpfobpafnhjhbajcjgccbbdofdckggg)
* [pry-byebug](https://github.com/deivid-rodriguez/pry-byebug)

#Do it for Yourself

* Branch name for this feature: 'getting_started'

This one is a little tricky for branch naming because our git repo won't exist until after we run rails new

So after we run rails new, we cd to the app directory and run ```git init```. Then, before we add or commit any files,
we run ```git checkout -b getting_started``` to create a switch to the new branch


+ Create your new app
+ Check that your have postgres and rspec included
+ Configure rspec with the ```.rspec``` file to display the documentation format so you can see all the tests that run (Research required)

__After__ you've made your changes, commit and push your branch up to your repo

```
	(getting_started)]$ git push --set-upstream origin getting_started
```

#Testing your Progress

What happens when you....?

* Run ```bundle install``` 
* Run ```rake db:create``` 
* Run ```rspec```
* Run ```rails s```
* View [http://localhost:3000/](http://localhost:3000/) while your server is running
* View [http://localhost:3000/page_that_does_not_exist](http://localhost:3000/page_that_does_not_exist) while your server is running
* Run ```git status```
* In Chrome Dev Tools open up the rails panel
* Run ```ls test``` - The test directory is for unit tests, your app should only have a ```spec``` directory.


#Update Your README.md

* Explain what you accomplished in this lesson
* Explain what the following gems do:
	* better_errors
	* quiet_assets
	* meta_request
	* awesome_print
	* pry_rails
	* binding_of_caller
	* pry-byebug
* What does `bundle install` actaully do?
* Why do we use Postgres instead of sqlite3?


