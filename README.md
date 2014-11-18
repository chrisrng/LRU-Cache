LRU-Cache
=========

This is an LRU (least recently used) cache implementation in JavaScript.

https://chrisrng.svbtle.com/lru-cache-in-javascript

It's very efficient and uses two data structures to manage the elements. A doubly-linked list and a map gives us the following:
- **Time complexity:** O(1)
- **Space complexity:** O(n)

This is achieved by having the doubly-linked list manage when we have to  rearrange the elements while the map gives us direct access to the resource. Look-up in a map is O(1) by providing the key. We introduce the concept of the "head", which is the least recently used entry, and the "tail", which is the most recently used entry, to keep track of the order when elements are retrieved or added. There are two pointers per node which is relatively low cost to manage the ordering.

**API:**
- lru(limit)
 - Initialize LRU cache with default limit being 10 items
- get(key)
 - Retrieve a single entry from the cache
- set(key, value)
 - Change or add a new value in the cache
 - We overwrite the entry if it already exists
- remove(key)
 - Remove a single entry from the cache
- removeAll()
 - Resets the entire cache
 - Argument limit is optional to be reset
- forEach(function(){})
 - Traverse through the cache elements using a callback function
 - Returns args [node element, element number, cache instance] for the callback function to use
- toJSON()
 - Returns a JSON representation of the cache
- toString()
 - Returns a String representation of the cache
