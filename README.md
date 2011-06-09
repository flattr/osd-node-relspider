RelSpider
=============

A quick proof of concept NodeJS library for spidering web linking relations like the XFN and  HTML5 author relations.

Example
--------

Example script for fetching and counting all "author" and "me" relations from http://example.com. Every call to relspider() fetches each non-fetched entry in result. So modifying the example to call it once again would fetch all relations found on http://example.com and check those pages for relations as well.

    var relspider = require('relspider'),
      result = {'http://example.com' : {}};
    
    relspider(function () {
      console.log('Found', result.length - 1, 'new relations');
    }, {
      directory : result
    });

A full example can be found at example/youtube-and-cli.js. It by defaults fetches 5 levels deep of relations starting from my (Pelle's) only YouTube video. It also takes command line arguments - the first one being a value for how many levels deep to look for relations and the rest one being URL:s which replaces the YouTube video as the starting point of the search.
