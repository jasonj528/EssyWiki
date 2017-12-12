# Users API

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