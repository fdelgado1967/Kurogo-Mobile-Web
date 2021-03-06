#################
News Module
#################

The news module shows a list of stories/articles from an RSS feed. If the feed provides full textual
content, the article is shown to the user in a mobile friendly format. If the feed does not contain
full text then the module will redirect the browser to the URL of the article.

======================
Configuring News Feeds
======================

In order to use the news module, you must first setup the connection to your data. There are
2 required values that must be set and a few optional ones. You can set these values by either using
the :ref:`admin-module` or by editing the *SITE_DIR/config/news/feeds.ini* file directly.

The module supports multiple feeds. Each feed is indicated by a section in the configuration
file. The name of the section should be a 0-indexed number. (i.e. the first feed is 0, the second feed
is 1, etc). The following values are required:

* The TITLE value is a label used to name your feed. It will be used in the drop down list to select
  the current feed
* The BASE_URL is set to the url of your News feed. It can be either a static file or a web service. 

**Optional values**

* CONTROLLER_CLASS - allows you to set a different class name for the controller. The default is 
  RSSDataController. You could write your own subclass to adjust the URL if your source is a 
  web service. 
* PARSER_CLASS set this to a subclass of *DataParser*. You would only need to change it if your data
  source returns data in a format other than RSS/Atom or RDF. The default is RSSDataParser.
* ITEM_CLASS allows you to set a different class name for each item in the feed. This would allow
  you to handle a feed that has custom fields
* ENCLOSURE_CLASS allows you to set a different class name for enclosures. This would allow you
  to handle custom behavior for enclosures, including images, video and audio.
