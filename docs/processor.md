# wiki.core.Processor

## Class Overview

This class handles the processing of .md files into their respective pages on the wiki. A processor is initialized with a string of text to be processed. The Processor's primary method is process(), which runs pre-processing, markdown processing, splitting content from metadata, metadata processing, and finally post-processing. Pre- and post-processing can involve any number of defined processing functions; in the current system the only one of these defined is the "wikilink" process that is included in the list of postprocessors. All wikilink does is add anchor tags linking to another page where the double bracket wiki links are used. Markdown processing mearly calls the conversion method from the markdown import. The split_raw() method, which splits content from metadata, merely does so by splitting on the first occurence of two newline characters; this is how the .md files separate meta attributes from content. The returned meta data is then parsed back into a dictionary with process_meta(). What is returned by the process() method finally is the post-processed final data, the original markdown after being split, and the metadata dictionary.

## preprocessors

## postprocessors