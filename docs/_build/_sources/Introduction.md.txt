# EssyWiki

## What is this?

EssyWiki is a fork of Riki by Dr. Samuel Cho. Riki itself is a fork of [Wiki2](https://github.com/alexanderjulo/wiki).

EssyWiki is a team project by Jason Johnson, Chris Garrett, and Logan Brown for Dr. Cho's CSC 440 Software Engineering Course taken Fall 2017.

The original project's purpose was to create a simple, easy to use wiki system based solely around the filesystem, the markdown language, and Flask.

## How does it work?

The wiki system is simple and directory-based, meaning the location of the markdown files used for each page's formatting and content have a direct mapping to their URL used to request them. These files can be uploaded to the server with an included upload page template or directly to the server (although they would have to follow proper url  conventions this way). The Wiki system is capable of easily indexing pages this way, by simply walking through the root directory. Pages contain metadata such as their title and any tags; these, along with the content body, can all be searched through the indexing methods of the Wiki system. All CRUD operations can be performed on Pages and Users, with HTML templates given for pages that can utilize these functions included in the installation. Forms executing these actions are extended from the WTForms library. Pages are displayed by converting markdown to HTML after stripping it of any metadata that the system adds to the top of the file. Users are stored on the server in users.json. The web framework backing Wiki is Flask; the app's config can be changed through config.py. Calling "wiki web" from the content directory will run the server using Flask with the directory content provided and as specified in config.py. 