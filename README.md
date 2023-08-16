# Features
1. Built in type checking for parameters passed to it's functions
2. Default headers setup aswell as optional per-route headers
3. Automatically setup to check for errors on response
4. Built in optional caching of responses with cacheTTL
5. Traditional lua library usage and Short hand usage options
6. Built in error handling and warnings to inform developer when they have done something incorrectly and how to resolve it


# Usage
>### api.Add( id, route, cback, onError, cacheTTL, customHeaders )
>Used to create a new API method

params:
	id				    string		  The ID for the method to call
	route			    string		  The route for the API to use
	cback			    function	  The callback function to run when the API responds
	onError			  function	  A callback function for custom error handling
	cacheTTL		  number		  Amount of seconds to cache the response from the API
	customHeaders	table		    Optional custom http headers to use for the route. will overide default API headers


>### api.Remove( id )
>Used to remove an API method

params:
	id		string		The method to be removed


>### api.Call( id, params )
>Used to call an API method

params:
	id		  string		The method to run
	params	table		  The parameters to pass to the API route


>### api.GetTable()
>Used to get the API method table

>### api.SetUrl( url )
>Used to set the current API url

params:
  url		string		The url for the API to use


>### api.AddHeader( header, value )
>Used to add a default API header

params:
	header		string		The default header to be added
	value		  string		The value to set the header to


>### api.SetHeader( header, value )
>Used to modify a default API header

params:
	header		string		The default header to be added
	value		  string		The value to set the header to


>### api.RemoveHeader( header )
>Used to remove a default API header

params:
	header		string		The default header to be removed


