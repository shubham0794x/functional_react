
## REST APIs In React Hooks With Fetch

In the project directory, you can run:

It uses functional components with hooks and the fetch API.

npm install

## Run on http://localhost:3000
npm start

# Build for prod
npm run build

APIs are what we can use to supercharge our React applications with data. There are certain operations that can’t be done on the client-side, so these operations are implemented on the server-side. We can then use the APIs to consume the data on the client-side.
APIs consist of a set of data, that is often in JSON format with specified endpoints. When we access data from an API, we want to access specific endpoints within that API framework. We can also say that an API is a contractual agreement between two services over the shape of request and response. The code is just a byproduct. It also contains the terms of this data exchange.
In React, there are various ways we can consume REST APIs in our applications, these ways include using the JavaScript inbuilt fetch() method and Axios which is a promise-based HTTP client for the browser and Node.js.

# AN EXAMPLE OF A REST API RESPONSE

The way a REST API is structured depends on the product it’s been made for — but the rules of REST must be followed.
The sample response below is from the Github Open API. We’ll be using this API to build a React app later on in this tutorial.
https://api.github.com/users/shubham0794x

## Consuming APIs Using The Fetch API
The fetch() API is an inbuilt JavaScript method for getting resources from a server or an API endpoint. It’s similar to XMLHttpRequest, but the fetch API provides a more powerful and flexible feature set.
It defines concepts such as CORS and the HTTP Origin header semantics, supplanting their separate definitions elsewhere.
The fetch() API method always takes in a compulsory argument, which is the path or URL to the resource you want to fetch. It returns a promise that points to the response from the request, whether the request is successful or not. You can also optionally pass in an init options object as the second argument.
Once a response has been fetched, there are several inbuilt methods available to define what the body content is and how it should be handled.
Consuming APIs Using The Fetch API
The fetch() API is an inbuilt JavaScript method for getting resources from a server or an API endpoint. It’s similar to XMLHttpRequest, but the fetch API provides a more powerful and flexible feature set.
It defines concepts such as CORS and the HTTP Origin header semantics, supplanting their separate definitions elsewhere.
The fetch() API method always takes in a compulsory argument, which is the path or URL to the resource you want to fetch. It returns a promise that points to the response from the request, whether the request is successful or not. You can also optionally pass in an init options object as the second argument.
Once a response has been fetched, there are several inbuilt methods available to define what the body content is and how it should be handled.
THE DIFFERENCE BETWEEN THE FETCH API AND JQUERY AJAX
The Fetch API is different from jQuery Ajax in three main ways, which are:
The promise returned from a fetch() request will not reject when there’s an HTTP error, no matter the nature of the response status. Instead, it will resolve the request normally, if the response status code is a 400 or 500 type code, it’ll set the ok status. A request will only be rejected either because of network failure or if something is preventing the request from completing
fetch() will not allow the use of cross-site cookies i.e you cannot carry out a cross-site session using fetch()
fetch() will also not send cookies by default unless you set the credentials in the init option.
PARAMETERS FOR THE FETCH API
resource
This is the path to the resource you want to fetch, this can either be a direct link to the resource path or a request object
init
This is an object containing any custom setting or credentials you’ll like to provide for your fetch() request. The following are a few of the possible options that can be contained in the init object:
method
This is for specifying the HTTP request method e.g GET, POST, etc.
headers
This is for specifying any headers you would like to add to your request, usually contained in an object or an object literal.
body
This is for specifying a body that you want to add to your request: this can be a Blob, BufferSource, FormData, URLSearchParams, USVString, or ReadableStream object
mode
This is for specifying the mode you want to use for the request, e.g., cors, no-cors, or same-origin.
credentials
This for specifying the request credentials you want to use for the request, this option must be provided if you consider sending cookies automatically for the current domain.

# BASIC SYNTAX FOR USING THE FETCH() API

## A basic fetch request is really simple to write, take a look at the following code:
https://api.github.com/users/shubham0794x/repos
  .then(response => response.json())
  .then(data => console.log(data));
Copy
In the code above, we are fetching data from a URL that returns data as JSON and then printing it to the console. The simplest form of using fetch() often takes just one argument which is the path to the resource you want to fetch and then return a promise containing the response from the fetch request. This response is an object.
The response is just a regular HTTP response and not the actual JSON. In other to get the JSON body content from the response, we’d have to change the response to actual JSON using the json() method on the response.
USING FETCH API IN REACT APPS
Using the Fetch API in React Apps is the normal way we’d use the Fetch API in javascript, there is no change in syntax, the only issue is deciding where to make the fetch request in our React app. Most fetch requests or any HTTP request of any sort is usually done in a React Component.
This request can either be made inside a Lifecycle Method if your component is a Class Component or inside a useEffect() React Hook if your component is a Functional Component.
For example, In the code below, we will make a fetch request inside a class component, which means we’ll have to do it inside a lifecycle method. In this particular case, our fetch request will be made inside a componentDidMount lifecycle method because we want to make the request just after our React Component has mounted.

