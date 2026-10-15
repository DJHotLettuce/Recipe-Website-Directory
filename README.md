# Recipe-Website-Directory
A crowd-sourced directory of high quality recipe websites. The websites are crawled and indexed to create a special purpose recipe search engine which can be found at https://iri.cooking

The theory behind this project is that a human managed web directory can serve as the basis for higher quality search engines. Because we're not crawling the entire web, the project requires very little compute resources.

Perhaps eventually, different special purpose search engines could be linked together to create a general purpose search engine. One that requires less maintenance and resources than traditional search engines while also delivering better results. (See [Similar Projects](#Similar-Projects))

## Contributing

Help is needed in order to scale up the list of websites so any submissions or suggestions are greatly appreciated

There are 2 ways to contribute links to the directory.
1. Submit links using the form at https://iri.cooking/contact.php
2. Fork this repo, add an entry to 'sites.ini' file according to the guidelines listed below. Then submit a pull request

## Submission Guidelines

The purpose of IRI.cooking is to help people avoid low quality cooking websites that are cluttered with ads. So we want to avoid low effort content farm sites, AI generated slop or anything with a lot of popup ads

Absolutely no video ads! They noticeably slow down browsers, especially for people using older devices

Static ads are acceptable. For example, if you have a blog that contains a banner promoting your new cookbook then that is fine. Or if a recipe on your site has a paid promotion then that is okay too. The ads that we’re avoiding are the embedded algorithmic popups created by internet advertising companies

An ad at the very bottom of a page is also fine so long as it is a static image or gif, not a video

## Project Status

IRI is a hobby project and still in development. The goal is to be a proof of concept for a new way to create search engines. If all goes well then, in theory, the same concept could be used to create a general purpose search engine
Also I like to cook and I think most of the popular recipe websites are terrible

## Directory Structure

The directory is an ini file which contains the website entries. Each entry contains some basic information about the site such as the title, URL, description, etc., followed by some filters that control which parts of the website the crawler should crawl and index. 
Because we only want to index recipes, we need to tell the crawler which sections of the site contain those. This is done with some regex patterns described below.

Example entry:

[Recipes from The Great British Bake Off]\
author=Love Productions\
info=The Great British Bake Off is the ultimate baking battle where passionate amateur baking fans compete to be crowned the UK’s Best Amateur Baker.\
tags=tv shows\
startURL=https://thegreatbritishbakeoff.co.uk/recipes \
crawlURLFilters=https://thegreatbritishbakeoff.co.uk \
scrapeURLFilters=thegreatbritishbakeoff.co.uk/recipes/ \
dontCrawlURLFilters=^https://thegreatbritishbakeoff.co.uk/bake-offs/,^https://thegreatbritishbakeoff.co.uk/your-bakes/,collection= \
dontScrapeURLFilters=

Required Fields:
1. [TITLE]
This is the title of the website
2. author=Author of site
3. info=A brief description of the site
tags=The Category or relevant words
4. startURL=Where the crawler should start crawling

Optional Fields:
These parameters are for the web crawler and don't need to be included
1. crawlURLFilters=A list of strings or regular expressions for which URLs the crawler should follow
2. scrapeURLFilters=A list of strings or regular expressions for which URLs the crawler should index
3. dontCrawlURLFilters=A list of strings or regular expressions for which URLs the crawler should explicitly avoid
4. dontScrapeURLFilters=A list of strings or regular expressions for which URLs the crawler should explicitly not index

## Similar Projects

https://feedle.world

https://marginalia-search.com

https://wiby.org
