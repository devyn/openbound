  OpenBound
=============

Theory
-------------
The whole theory behind OpenBound is that social networks are too central. This can lead to insecurity of data and privacy issues. With OpenBound though, __everyone__ hosts their own "bind".

For example, Jack and Jill want to become OpenBound friends. To do that, either Jack or Jill would click on "add friend" and type in the other's URL. So, Jack's site is http://binds.example.com/~jack and Jill vice versa. So, Jack goes to his site and clicks on "add friend" and types in http://binds.example.com/~jill. Jack's bind invisibly sends a POST request to Jill's bind. Then, Jill logs on to her site and sees a notification asking whether she would like to accept. Jill clicks on her answer, and either way, her bind POSTs to Jack's site.

This way, everyone's happy, and it's only slightly more complex.
