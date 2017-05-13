

http://stackoverflow.com/questions/671118/what-exactly-is-restful-programming?rq=1
https://martinfowler.com/articles/richardsonMaturityModel.html
http://web.archive.org/web/20130116005443/http://tomayko.com/writings/rest-to-my-wife
http://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm


# Representational State Transfer (REST)
#### Ultimately what REST is is just a series of rules in place for your server

#### Constraints 

1) Client -Server : 
 client sends a request, server sends a response

2)Stateless server : 
 Stateless

 We next add a constraint to the client-server interaction: communication must be stateless in nature, as in the client-stateless-server (CSS) style of Section 3.4.3 (Figure 5-3), such that each request from client to server must contain all of the information necessary to understand the request, and cannot take advantage of any stored context on the server. Session state is therefore kept entirely on the client.
Communicate statelessly
As the load from the client increases on your server you start to add more servers to the mix and when 
that happens now you get into a situation where the server may contain some information about the client that doesn't transfer from one 
server to the other. 
   Ultimately the client sends a request to the server and it doesn't matter what server it goes to, 
   so everything that the server's going to need to process this **request should be included in that request**,
   and then based on that request and based on all that information that's in the request it'll send a response to the server. 
   If you find yourself on the server storing information about the request or about the client, then you're not writing a truly 
   RESTful service.
 
3) constraint of caching
ultimately as servers are sending responses back full of data, sometimes you're sending back data that doesn't change very often, 
so think about a list of clients or a list of book authors or something along those lines. That data's not going to change between now 
and 5 minutes from now the next time the client pulls that data, so this constraint says let the client know how long this data is
good for, so that the client doesn't have to come back to the server for that data over and over again.

4)Every resource is uniquely addressable using a uniform and minimal set of commands (typically using HTTP commands of GET, POST, PUT, or
DELETE over the Internet)

5)Uniform Interface
  Resource :
  
  you're dealing with a RESTful service you'll be dealing with a resource or a series of resources and all that really means is 
  you're dealing with nouns. Uniform Interfaces are built around things, not actions. Sometimes when you call a service it'll
  be authorize or login. Those are verbs. In ReST everything we're going to be dealing with is nouns, so for this project we're 
  going to be working with books and authors. Both of these are the resources that each of our ReSt services will be dealing with. 
  For example, dealing with a book, the URL will be HTTP://something/book. If we're dealing with authors it would be /author.

 HTTP verbs :
 
 The HTTP verbs that we use I our request will dictate the type of activity we're trying to do on the resource. 
 For example, our HTTP Get will simply request data, so I'm just trying to get data, and it'll either return a list of objects
 or a specific object. 
 The post is used to add data, so if I do post to a /book I'm going to add a new book. 
 Delete will remove. 
 Put is used to update, so if I would just want to update or replace  a resource I use Put. Patch is coming more into favor now too for just updating a piece of our resource. 
 Put updates the entire resource, patch will just update a piece of that resource.

HATEOS :
Hypermedia as the Engine of Application State, which I know is not very descriptive at all. Basically all that means is that in 
each request will be a set of hyperlinks that you can use to navigate the API. It's just the API's way of
letting you know what other actions you can take on this particular resource





References :
https://www.infoq.com/articles/rest-introduction
https://app.pluralsight.com/library/courses/node-js-express-rest-web-services/transcript
