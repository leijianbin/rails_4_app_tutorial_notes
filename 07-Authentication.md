Level 07 - Authentication With Devise
-----------

#Overview
* Install Devise
* Add a root route to the hello world action
* Install the Devise Views
* Allow Users to Register
* Allow Users to Login
* Allow Users to Logout
* Restrict All things routes to logged in users
* Redirect to the things index page on login
* Redirect to the root page on logout
* HARD BIT: Fixing Tests to Work with Authentication
* Bonus: Update Devise views to match bootstrap

#Level Resources

* [https://github.com/plataformatec/devise#getting-started](https://github.com/plataformatec/devise#getting-started)
* [http://guides.rubyonrails.org/routing.html](http://guides.rubyonrails.org/routing.html)
* [http://blog.sorryapp.com/2013/03/22/request-and-controller-specs-with-devise.html](http://blog.sorryapp.com/2013/03/22/request-and-controller-specs-with-devise.html)


#Do it for Yourself

* Branch name for this feature: 'authentication'

* Run ```git checkout -b authentication``` to create a switch to the new branch

* Add your root route to the hello world page

* Add Devise to your app and create a User model

* Install the Devise Views

* Add an Authentication check to all actions on the Things controller

* Investigate how to set the redirects on login and logout and implement: 
	* Redirect to things index on login
	* Redirect to root route on logout
	
* Run ```rspec``` Uh-oh :)
	* Now we fix our controller tests for ```ThingsController``` in this case we need to update the tests, not what we would normally do, but pay attention and there is much to be learned relating to how to write test for your authentication
	* This is tricky and this is my attempt:
	[https://github.com/stujo/rails_4_app_tutorial/commit/0e6f0db3ef0eef3194a0d60f26378bfa75ebe7dc#diff-5fa8dda64b8bab4096bf3ef4b9385c1f](https://github.com/stujo/rails_4_app_tutorial/commit/0e6f0db3ef0eef3194a0d60f26378bfa75ebe7dc#diff-5fa8dda64b8bab4096bf3ef4b9385c1f)
	* Basically I wrapped all the current tests in a context that signs in a fake user (Created Via FactoryGirl) using the devise test helpers
		* removed let(:valid_session) { {} } and references to valid_session in ```spec/controllers/things_controller_spec.rb```
	    * Reviewed or create our FactoryGirl factory for users:
```spec/factories/users.rb``` based on errors I got without updating these
		* It would be a good idea to test that our authentication is working correctly
	* Also deleted ```spec/requests/things_spec.rb``` since it duplicates our controller test and 
		


* Add login, logout and register links to your nav menu, using helpers

* Ensure that the login and register links are only visible to unauthenticated users

* Ensure that the logout link is only visible to authenticated users

__After__ you've made your changes, commit and push your branch up to your repo

```
	(seeding)]$ git push --set-upstream origin authentication
```

#Testing your Progress

What happens when you....?

* Run ```rspec```
* Run ```rake routes```
* Run ```rails s```
* View [http://localhost:3000/things](http://localhost:3000/things) while your server is running
* View and Edit some of the seeded Thing
* DELETE ALL YOUR DATA! - Run ```rake db:reset```

#Update Your README.md

* Explain what you did
* Explain each of these devise behaviours:
	* Confirmable
	* Recoverable
	* Registerable
	* Rememberable
	* Trackable
	* Timeoutable
	* Validatable
	* Lockable
* What did you have to do to update your rspec tests after adding authentication for the ```things```	
* What are the routes that were added and what do they do?


