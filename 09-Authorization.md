Level 09 - Authorization!
-----------

#Overview
* Fix the controller to reflect the changes we made to our models
* Make sure users can only delete and edit their own Things
* Use partials to prevent repetition of code

#Level Resources

* [Layouts and Rendering Rails Guide](http://guides.rubyonrails.org/layouts_and_rendering.html)
* [Devise Documentation](http://devise.plataformatec.com.br/)



#Do it for Yourself

* Branch name for this feature: 'authorization'

* Run ```git checkout -b authorization``` to create and switch to the new branch

Try to create a new Thing in your browser.  Does it work?  If not, why?

We need to fix our controller methods to reflect the changes we made to our models yesterday.

The first thing we should do is fix our `create` method.  When a new Thing is created, we need to associate it with the user that created it.

Next, let's fix our `Edit` method.  Make sure that a user can only edit a thing that he/she created. If the user doesn't have permission to edit a Thing, redirect somewhere and display a "You don't have permission to do that" error message.

Similarly, fix `Destroy` to make a user can only delete his/her Things.  If the user doesn't have permission to delete a Thing, redirect somewhere and display a "You don't have permission to do that" error message.

You may have noticed that the code you added to `Edit` and `Destroy` is very similar. Move the authorization code to its own method.  Call it before any necessary actions using a before_action.

Next, let's make sure to hide the `edit` and `delete` links on the index page for posts that the logged in user does not own. 

Similarly, fix the `show` view so that it doesn't display an `edit` link to users that do not own the Thing.

Next, we're going to make a brand new page that willd display all of the Things that belong to the logged in user.  Let's call it `my_things`.

Create a route for `my_things`.  

Then, add the `my_things` method to the Things controller.  Retrieve all the Things that belong to the logged in user.

Lastly, create the `my_things` view.  In the view, display each Thing with its respective `edit`, `show`, and `delete` links.

You may have noticed that your `my_things` view and `index` view are extremely similar.  Move the repeated code to a partial to prevent repetition.

Pat yourself on the back.

__After__ you've made your changes, commit and push your branch up to your repo

```
  (seeding)]$ git push --set-upstream origin ownership
```

#Testing your Progress

What happens when you....?

* Try to make a new Thing in your browser?
* Run ```rspec```
* Try to access an edit page for a Thing that doesn't belong to you
* Try to access a delete page for a Thing that doesn't belong to you

#Update Your README.md

* Explain what you did
* What happens if you put the `flash[:errors]` after the redirect?  Before?
* What is the different between the flash hash and `notice`?
* Why do we use partials?  
* What is a before_action?  Why do we use them?



