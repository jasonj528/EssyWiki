# wiki.web.User

## Class Overview

This class encapsulates data about a user in the system. A User object is created with a manager, a name, and a dictionary of data. Dictionary values can be retrieved or changed with get() and set(), and this data can then be saved to the manager through save(). The is_authenticated(), is_active(), and is_anonymous() methods return a given boolean for the corresponding key in the dictionary, although is_anonymous() isn't yet implemented. Finally there is a check_password() method, which returns whether a password can authenticate the user with the user's specified authentication method. Passwords may be a salted hash or a cleartext, or authenticated with any method the developer may add (for now only the two present are checked, so any other will raise an exception).

###update_role

This method was created to allow an administrator easily update user roles. It does so by taking a string with the role, given by way of the user index, and then changes the roles attribute of the current user.