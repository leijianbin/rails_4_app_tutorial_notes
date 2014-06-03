Level 03 - Bootstrap 3
-----------

#Overview
* Add bootstrap 3 to application / layout
* Add Bootstrap generators (because we want bootstrap compatible templates)

#Level Resources
* [https://github.com/twbs/bootstrap-sass](https://github.com/twbs/bootstrap-sass)
* [http://getbootstrap.com/components/#navbar-default](http://getbootstrap.com/components/#navbar-default)
* [bootstrap-generators](https://github.com/decioferreira/bootstrap-generators)
* [iPhone viewport syntax](https://coderwall.com/p/p8obqw)

#Do it for Yourself

* Branch name for this feature: 'bootstrap'
* Run ```git checkout -b bootstrap``` to create a switch to the new branch

* Add the ```bootstrap-sass``` gem to the Gemfile (no need to include version number)

```
	gem 'bootstrap-sass'
	gem 'bootstrap-generators', '~> 3.1.1'

```

* Add the bootstrap generators gem by following the instructions in the README up to and including the ```rails generate bootstrap:install -f``` line

* __DO NOT__ run the scaffold generator itself! We will do that in a later level

* Ensure that the bootstrap styles are loaded on the helloworld page

* Make sure that your RSpec tests still passes


* Check that you included the required bootstrap javascript, your dropdowns may not work
* Add this rspec feature test in ```spec/features/nav_bar_spec.rb```

```

require 'spec_helper'

feature 'Nav Bar' do
  scenario 'links to Hello World' do
    visit helloworld_path
    expect(page).to have_css '.navbar ul li a[href=\'/helloworld\']', :text => 'Hello World'
  end
end


```

* Add your application name and a link to helloworld in the navbar
	* Use the both link_to and helloworld_path helpers!

* Check that the test given above runs and passes

* If you want to have a responsive design on mobile devices then the view port zoom for iPhones etc. (Research Required)

* __BONUS__: Customize the background color of your navbar (bootstrap generators uses the inverse navbar by default) (Research Required)

* __BONUS__: Apply the active style to the /helloworld navbar link if this is the current page (Research Required)


__After__ you've made your changes, commit and push your branch up to your repo

```
	(bootstrap)]$ git push --set-upstream origin bootstrap
```

#Testing your Progress

What happens when you....?

* Run ```rspec```
* Run ```rails s```
* View [http://localhost:3000/helloworld](http://localhost:3000/helloworld) while your server is running
* Resize your browse window to make it the same size as a mobile phone screen


#Update Your README

* What is bootstrap?
* What is responsive design?
* What is sass in `bootstrap-sass`?
* Where do all the bootstrap files go when you install the gem?
* What does this line ` *= require_tree .` in your application.css do?  Make sure you understand this!
* What is the Rails Asset pipeline? Read this [Rails Guide](http://guides.rubyonrails.org/asset_pipeline.html) and then write a few sentences explaning the asset pipeline.



