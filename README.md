# Overview:

The basic idea behind this was to use regular expression matching to locate keywords. The higher number of keyword exists in the page, the more likely it's to be the related page. The key parameter here is the threshold count. With limited time, I don't get the chance to play with it and thus used a random number of 10. 
There are is always the trade-off of the number of pages that match the criteria and how accurate each page is. With stricter criteria, it will take too long to look for the 1000 pages required, and therefore an acceptable solution should have some number of falsely selected pages. With the huge penalty of a falsely selected page, I've selected to go with the stricter one, and therefore due to runtime limitation, not able to get to the 1000 number.

# Regex strategy:

I experimented with multiple strategies:
1) In the <meta> tag, one can identify whether the language of the page in English. An English written page is more likely to be the one of interest.
2) In the <meta> tag, one can identify whether the keyword contains "covid". A carefully written <meta keyword> is more likely to be the one selected.
3) In the URL, one can expect the pages coming from a creditable news source such as cnn.com to be more reliable and therefore being more likely to be related.
4) Within the whole page, the higher number of times "covid"/"economy" exists, the more likely it is the page selected.

And the end, due to the aforementioned trade-off, 2) and 4) are selected to be the criteria of regex matching.

# Outstanding issue:

The 6 hour time window isn't quite enough for me to get to 1000 as the aforementioned trade-off says. One strategy is to parallelize the search since python isn't a language that is known for its speed. Still, with strict criteria, getting to 1000 within 6 hours is not possible for me.

