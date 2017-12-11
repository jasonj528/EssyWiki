# wiki.core.Page

## Class Overview

This class encapsulates the web page created by the Wiki system for any given .md file. Its constructor takes a path to a file, a URL, and a boolean stating whether the page is a new object. If the page is not new, the page calls its methods to load the file's contents and process the content via the Processor class to return the html data, body data, and metadata. The class also has a method save() which takes a boolean representing whether the action is an update; this function attempts to write the page to a local file, as well as loading and rendering the file if this is an update action. Metadata for pages are placed at the start of the file and are split from it when processed by splitting on the first occurence of a double newline character.