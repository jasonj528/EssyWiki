# wiki.web.UserManager

## Class Overview

This class handles the storing of user data as JSON in the file "users.json". Simply put all this class does is provide CRUD methods for Users, with add_user() and get_user() also returning a User object to be used. Additionally, it will store a salted hash if that authentication method is chosen. Users can be added as active or inactive, and with any number of roles supplied also.