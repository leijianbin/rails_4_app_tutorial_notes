Level 02 - Hello World with RSpec
-----------

#Overview
* Add a ```PagesController``` with a ```helloworld``` action
* Add Capybara feature test to make sure it works

#Level Resources
* [http://guides.rubyonrails.org/command_line.html#rails-generate](http://guides.rubyonrails.org/command_line.html#rails-generate)
* [http://robots.thoughtbot.com/how-we-test-rails-applications](http://robots.thoughtbot.com/how-we-test-rails-applications)
* [https://github.com/jnicklas/capybara](https://github.com/jnicklas/capybara)
* [https://relishapp.com/rspec/rspec-rails/v/3-0/docs/view-specs/view-spec](https://relishapp.com/rspec/rspec-rails/v/3-0/docs/view-specs/view-spec)

#Do it for Yourself

* Branch name for this feature: 'helloworld_rspec'
* Run ```git checkout -b helloworld_rspec``` to create a switch to the new branch

* Add Capybara to our app (Research Required)

* Write an RSpec Feature test to check that ```/helloworld```  displays a page which contains an ```<h1>``` tag with the content Hello World:
	* Create the file ```#spec/features/hello_world_spec.rb``` with this content: 

```
require 'spec_helper'

feature 'User wants greeting' do
  scenario 'says Hello World' do
    visit helloworld_path
    expect(page).to have_css 'h1', :text => 'Hello World', :visible => true
  end
end

```

* Run your RSpec test and check that it fails!
* Now make the test pass, starting by adding a ```/helloworld``` route mapping to the yet to be writtent PagesContoller's ```helloworld``` action, give that route the name ```helloworld``` (Research Required)
* Use the controller generator to create the PagesController pass ```helloworld``` as an action
* Get the tests to pass by completing the action and the view
* Commit your changes to git
* Remove all the files that the generated created that we don't need
	* app/assets/javascripts/pages.js.coffee 
	* app/assets/stylesheets/pages.css.scss
	* app/helpers/pages_helper.rb
	* spec/helpers/pages_helper_spec.rb
	* spec/views/pages/helloworld.html.erb_spec.rb 
* Remove the route added by the generator in routes.rb (since we have our own):
	* ``` # get 'pages/helloworld'```
	
	
* When you use generators in the future remember to clean up what you don't need!
* Commit your changes to git (Including Deleted Files)
* Make sure that your RSpec test still passes

__After__ you've made your changes, commit and push your branch up to your repo

```
	(helloworld_rspec)]$ git push --set-upstream origin helloworld_rspec
```

#Testing your Progress

What happens when you....?

* Run ```rspec```
* Run ```rails s```
* View [http://localhost:3000/](http://localhost:3000/) while your server is running
* View [http://localhost:3000/helloworld](http://localhost:3000/helloworld) while your server is running


#Update Your README.md

* Explain what you accomplished in this lesson
* What does Capybara do?
* What files does the rails controller generator create?  List them all.
* What does this line do? `(helloworld_rspec)]$ git push --set-upstream origin helloworld_rspec`
* What is the spec_helper?





