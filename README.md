# REST-Less

REST-less is a stand alone cache server specifically for Restful endpoints.
It provide cache flexibility per end point level, and further tuning of cache key entry determination.


REST-less is black box to your application and kind of front-end proxy, which hits your service whenever there is a cache miss.
You can configure your end point caching configuration in a RESTFul way. So you dont need not worry about the implemetation details.
All you do is configure the cache for your endpoint needs.


No downtime on your cache configuration update, as you can add and remove the cache configuration near real time using RESTFul


REST-less will be implemented via In - Memory with background replica updates. Hence should be lightning fast.


# Use cases:


1. Cache per endpoint should be easily turned on and off based on cache-control HTTP header.


2. Configuration for size, eviction poilcy, TTL  per endpoint. 
   

3. If there is no cache config found for the your service end point, then it wont cache.


4. Support below both url caching

   Static/fixed url (No path variable) Dynamic url (with path variable with RegEx support)


5. Add support for specific (few / all) query parameters to differentiate cache key


6. Add support for specific request payload parameter value using xpath to differentiate cache key




# Optimisation:

1. Deduplication, Group the cache keys which has same response
2. Optimise the cache to handle the limit and offset query params intelligently
3. Expire as part of successful modification of existing key, untill no expiry


# Corner cases:

1. if one of the header is added for the url then neeed to expired old entries 
2. Cache should consider failure response, and successful reesponse differently



