Level 08 - Associations!
-----------

#Overview
* Make ```Thing``` belong to ```User```
* ```User``` has_many ```Thing```s
* Update Seed File to reflect new model associations

#Level Resources

* [Active Record Associations Rails Guide](http://guides.rubyonrails.org/association_basics.html)
* [Migrations Rails Guide](http://guides.rubyonrails.org/migrations.html)



#Do it for Yourself

* Branch name for this feature: 'ownership'

* Run ```git checkout -b ownership``` to create and switch to the new branch

Create a new migration to add a `User` reference to our `Thing` model.  What's the difference between `user:references` and `user_id:integer`? You can use either one in this case, but they are not the same! Make sure you understand this before moving on.

Run `rake db:migrate`

Add the proper model associations between User and Thing.  has_many? has_one?  belongs_to?

Now that we have our models assocated, let's add a validation to the Thing model.  Write code to make sure a Thing is created with a user_id.

Reset the database and then re-seed the database.

Oh no! Our seed file doesn't work anymore.  What's wrong? Figure out a way to fix it.  Hint: you need to add a User!

Open your rails Console and make sure that you have at least one User in your database.  Check to make sure that User has multiple Things associated with it.

Pat yourself on the back.


__After__ you've made your changes, commit and push your branch up to your repo

```
	(seeding)]$ git push --set-upstream origin ownership
```

#Testing your Progress

What happens when you....?

* Try to make a new Thing in your console?
* Try to make a new Thing in your browser?
* Run ```rspec```
* Delete a specific User.  What happens to its associated Things?

#Update Your README.md

* Explain what you did
* What is the relationship between has_many and belongs_to?
* What is a foreign key?
* What actually happens when we add associations between models?
	* What does it do behind the scenes?  
	* How does it allow us to shorten our controller methods?  Think about what your code would look like if you couldn't use model associations.
* There are 6 model associations.  What are they? Explain each one and give an example of when you might use each one.
* How do Rails migrations work?  
* Do you need to name a migration anything specific?  Are ther
* What's the difference between `user:references` and `user_id:integer`
* How do you undo a migration?



