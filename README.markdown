  OpenBound
=============

Theory
-------------
The whole theory behind OpenBound is that social networks are too central. This can lead to insecurity of data and privacy issues. With OpenBound though, __everyone__ hosts their own "bind".

For example, Jack and Jill want to become OpenBound friends. To do that, either Jack or Jill would click on "add friend" and type in the other's URL. So, Jack's site is http://binds.example.com/~jack and Jill vice versa. So, Jack goes to his site and clicks on "add friend" and types in http://binds.example.com/~jill. Jack's bind invisibly sends a POST request to Jill's bind. Then, Jill logs on to her site and sees a notification asking whether she would like to accept. Jill clicks on her answer, and either way, her bind POSTs to Jack's site.

This way, everyone's happy, and it's only slightly more complex.

Proposed WAY
-------------
* Jack clicks on "Add Friend", and types in Jill's bind URL.
* Jack's bind creates a new "tracking" object, that is, a record with a 128-bit (32-digit) hexidecimal ID, the string 'outgoing', and Jill's URL.
* Jack's bind POSTs to /api/track with data about the "tracking" object, causing Jill's bind to create a new "tracking" object with that data and instead of "outgoing", "incoming".
* The next time Jill logs on to her bind, she is prompted about the friend request and presses YES.
* Jill's bind POSTs to /api/track-authorize on Jack's bind with information about that tracking object, and the response (YES or NO) and Jack's bind responds with either CONFIRMED or DENIED.
* If CONFIRMED, Jack **and** Jill's binds **both** add a "friend" object with the "tracking" ID and delete the "tracking" object.
* However, if DENIED, the friend request was most likely faked and both Jack and Jill will be notified.

Proposed Interface
--------------------
* clean
* apps or widgets or something?
* customizable
* lifestreaming, public, friend and private options
* fast

