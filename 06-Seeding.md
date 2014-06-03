Level 06 - Seeding the Database
-----------

#Overview
* Add some seed data 
* Understand find_or_create_by
* Use Array.sample
* Use the forgery gem to generate descriptions

#Level Resources

* [http://www.railszilla.com/rails-seed-data-example/rails](http://www.railszilla.com/rails-seed-data-example/rails)
* [http://apidock.com/rails/v4.0.2/ActiveRecord/Relation/find_or_create_by](http://apidock.com/rails/v4.0.2/ActiveRecord/Relation/find_or_create_by)
* [http://stackoverflow.com/questions/3482149/how-do-i-pick-randomly-from-an-array](http://stackoverflow.com/questions/3482149/how-do-i-pick-randomly-from-an-array)
* [https://github.com/sevenwire/forgery](https://github.com/sevenwire/forgery)
* [http://listofrandomwords.com/](http://listofrandomwords.com/)

#Do it for Yourself

* Branch name for this feature: 'seeding'

* Run ```git checkout -b seeding``` to create a switch to the new branch

* Open ```db/seeds.rb``` this is where you'll do your work today!

* Add 3 or 4 ```Thing.find_or_create_by``` statements with different hard coded data values for ```name``` and ```description```

* Come up with a way to populate the database with 200 more Things with random data:
    * Install the forgery gem

	* Each thing should be a bit random, including at least two random English words in it's name

	* Use Array.sample to pick random words from a list of English words defined in Ruby in your ```db/seeds.rb```

	* Use the forgery gem to populate Things' description fields with: ```Forgery(:lorem_ipsum).words(30, :random => true)```


__After__ you've made your changes, commit and push your branch up to your repo

```
	(seeding)]$ git push --set-upstream origin seeding
```

#Testing your Progress

What happens when you....?

* Run ```rake db:seed``` 
* Run ```rails s```
* View [http://localhost:3000/things](http://localhost:3000/things) while your server is running
* View and Edit some of the seeded Thing
* DELETE ALL YOUR DATA! - Run ```rake db:reset```

#Update Your README.md

* Explain what you did
* Explain what is the difference between .find_or_create_by and find_or_initialize_by
