# wiki.web.routes

This file defines the routes that the wiki will navigate in order to get to certain pages. @bp.route(URL) is used to tell Flask to call the specifed function when a user types in a given URL. 

### home(url)
The default route when a user signs on to the wiki is defined by '/'. 

### index()
'/index' is used to direct users to an index of all of the current wiki pages created by other users. 

### display(url)
display(url) takes the specified string and gets the page with the string's name. It then renders the template of the corresponding page.

### create()
This function is called when the user wants to create a new page for the wiki. It displays the create.html page, and when the user submits their new page, it redirects the user to that new page.

### edit(url)

This function takes a string that the user types into the URL, and then redirects the user to the editor for that specific page. When the user clicks the submit button, it submits the changes and redirects the user back to the wiki page.

### preview()

This functions allows the user to preview the work they are doing while editing a page.

### move(url)

This function allows the user to move a specified page from one URL to another. This is done by using a built-in function of the wiki to delete the page and empty the former URL, and creating a new page with the current page's contents and new URL. It then redirects the user to the new page when they submit.

### delete(url)

This function allows a user to delte a specified page. It does so through the path '/delete/<path:url>'. In our implementation, we decided that this function should only be a valid function of the administrator, so that data is not deleted by unauthorized members who may have malicious intentions. If the current user is an admin, the page is deleted and the user redirected to the home page, where a flash message will tell them of their success. If they are not logged in as an admin, they will simply be redirected to the homepage and alerted that their action has failed.

### tags()

This function directs the user to a list of all of the tags created for the wiki.

### tag(name)

This function takes the tag that the user has selected, either from the tags page, or from the URL, and returns to them the search result of their tag search.

### search()

This function provides the user with a search form, where upon submitting they will by given a list of results of their search. 

### addUser()

This function was added by EssyWiki. It provides an administrator with a form to add a new user. When they submit the form, it checks to see if the user already exists, and if it does not, creates the new user with the specified attributes. If the user does exist, it provides them with an error message saying so. 

### user_login()

This function displays the user login form, and upon submission calls the login_user method with the specified user attributes. If the login is successful, it directs the user to the index with a message saying as much. If unsuccessful, it prompts the user to log in with different information and displays an error.

### user_logout()

This function simply sets the current user's authenticated and active attributes to false, logging the user out. They are then directed to log in again.

### user_index()

This function displays to the user a list of all of the users that have accounts on the wiki. 

### user_changerole(name, role)

This function allows an administrator to change the role of another user. It then calls upon the user manager to update the role to the users.json file. If the user is not an administrator it simply redirects them to the user index and gives them an error.

### user_delete(name)

This function takes a username and deletes them from the users.json file. This action is locked to administrators only, and gives an error to any other users that try to access it. 