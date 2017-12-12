# Pages API

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
