Level 04 - Scaffolding
-----------

#Overview
* Use the scaffold generator to kick-start our app development

__EDITOR'S NOTE__: There are people that don't like scaffolds, they produce large numbers of files and there's a temptation to NOT understand what is going on and just skip forwards.

I've chose to introduce them here, because I feel a fully scaffolded example can provide some insight into rails and it's workings. I don't recommend you use them all time, but I want you to have one full MVC with Tests that you can use as a reference. All generators, and scaffolds in particular, produce files you may never use, it's good practice to remove them, it's also __ESSENTIAL that you remove controller methods which you don't want to expose__. In order to do this correctly you must understand all the code that is generated, so you know what to remove.

Take the time to understand the code, or don't use scaffold


#Level Resources

* [rails generate scaffold](http://guides.rubyonrails.org/command_line.html#rails-generate)

#Do it for Yourself

* Branch name for this feature: 'scaffolding'
* Run ```git checkout -b scaffolding``` to create a switch to the new branch


* We are going to use the scaffold generator to create our model along with a set of common views and routes, it takes the same arguments as the model generator you've used before, it does the same thing and more!

* Each ```Thing``` has:
	* ```name:string``` - The name of the thing
	* ```description:text``` - A free form text description

* Learn about scaffold generators and run it carefully to create the ```Thing``` model:

```
$ rails generate scaffold Thing name:string description:text 
```


* ___Review all the changes and UNDERSTAND how EVERYTHING works, 
THIS IS MANDATORY, DO NOT SKIP THIS STEP. YOU MUST VALIDATE YOUR UNDERSTANDING OF THE RAILS FRAMEWORK AT THIS TIME!___

What is each of these files?

```
      invoke  active_record
      create    db/migrate/20140528055411_create_things.rb
      create    app/models/thing.rb
      invoke    rspec
      create      spec/models/thing_spec.rb
      invoke  resource_route
       route    resources :things
      invoke  scaffold_controller
      create    app/controllers/things_controller.rb
      invoke    erb
      create      app/views/things
      create      app/views/things/index.html.erb
      create      app/views/things/edit.html.erb
      create      app/views/things/show.html.erb
      create      app/views/things/new.html.erb
      create      app/views/things/_form.html.erb
      invoke    rspec
      create      spec/controllers/things_controller_spec.rb
      create      spec/views/things/edit.html.erb_spec.rb
      create      spec/views/things/index.html.erb_spec.rb
      create      spec/views/things/new.html.erb_spec.rb
      create      spec/views/things/show.html.erb_spec.rb
      create      spec/routing/things_routing_spec.rb
      invoke      rspec
      create        spec/requests/things_spec.rb
      invoke    helper
      create      app/helpers/things_helper.rb
      invoke      rspec
      create        spec/helpers/things_helper_spec.rb
      invoke    jbuilder
      create      app/views/things/index.json.jbuilder
      create      app/views/things/show.json.jbuilder
      invoke  assets
      invoke    coffee
      create      app/assets/javascripts/things.js.coffee
      invoke    scss

```


* Review the created migration 

* Run ```rake db:migrate```

* Add a link to the ```Thing``` index action to the nav menu, using helpers

* Run RSpec

__After__ you've made your changes, commit and push your branch up to your repo

```
	(scaffolding)]$ git push --set-upstream origin scaffolding
```

#Testing your Progress

What happens when you....?

* Run ```rspec```
* Run ```rails s```
* Run ```rake routes```
* View [http://localhost:3000/things](http://localhost:3000/things) while your server is running
* Add some Things
* Run ```rails c``` 
	* Try ```Thing.all``` 	

#Update Your README

* List every file that the scaffold created for you 
* Explain the code that was created in each of those files
* **DO NOT MOVE ON UNTIL YOU UNDERSTAND EVERY SINGLE THING THE SCAFFOLD DID FOR YOU.  I'M NOT JOKING!  SPEND MULTIPLE HOURS IF YOU NEED TO**.  
* What code can we remove from the generated files?
* Explain the arguments for and against using scaffolds.
