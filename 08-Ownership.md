Level 08 - Users and Things
-----------

#Overview
* Make ```Thing``` belong to ```User```
* ```User``` has_many ```Thing```s
* Update Seed File to include Users

#Level Resources



#Do it for Yourself

* Branch name for this feature: 'ownership'

* Run ```git checkout -b ownership``` to create a switch to the new branch


__After__ you've made your changes, commit and push your branch up to your repo

```
	(seeding)]$ git push --set-upstream origin ownership
```

#Testing your Progress

What happens when you....?

* Run ```rspec```
* Run ```rake db:migrate```
* Run ```rake routes```
* Run ```rails s```
* View [http://localhost:3000/things](http://localhost:3000/things) while your server is running
* View and Edit some of the seeded Thing
* DELETE ALL YOUR DATA! - Run ```rake db:reset```
* Re-seed database

#Update Your README.md

* Explain what you did
* What is the relationships between has_many and belongs_to



