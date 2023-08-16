# What this is meant to be used for
For publicly usable APIs and retrieving data that needs to be cached and updated in intervals, and to do so with most of the logic behind it already written for you.


# What this is not meant to be used for
Dealing with anything that requires authentication or authorization. You will need to implement these two things yourself. This may change later but for now this is not something I have the time or motivation to bother with.


# Features
1. Built in type checking for parameters passed to it's functions
2. Default headers setup aswell as optional per-route headers
3. Automatically setup to check for errors on response
4. Built in optional caching of responses with cacheTTL
5. Traditional lua library usage and Short hand usage options
6. Built in error handling and warnings to inform developer when they have done something incorrectly and how to resolve it


# Usage
Make sure that you run api.SetURL( "your url here" ) before attempting to use api.Call( ... ) otherwise the library will intentionally refuse to attempt making any requests as it would simply error anyways without a set url.

## api.Add( id, route, cback, onError, cacheTTL, customHeaders )
Used to create a new API method

PARAMETER | TYPE | DESCRIPTION
--- | --- | ---
id | string | The ID for the method to created
route | string | The route for the API to use
cback | function | The callback function to run when the API responds
onError | function | A callback function for custom error handling
cacheTTL | number | Amount of seconds to cache the response from the API
customHeaders | table | Optional custom http headers to use for the route. will overide default API headers

## api.Remove( id )
Used to remove an API method

PARAMETER | TYPE | DESCRIPTION
--- | --- | ---
id | string | The method to be removed

## api.Call( id, params )
Used to call an API method

>Shorthand way to call a method would be **api( id, params )**

PARAMETER | TYPE | DESCRIPTION
--- | --- | ---
id | string | The method to run
params | table | The parameters to pass to the API route

## api.GetTable()
Used to get the API method table

## api.SetUrl( url )
Used to set the current API url

PARAMETER | TYPE | DESCRIPTION
--- | --- | ---
url | string | The url for the API to use

## api.AddHeader( header, value )
Used to add a default API header

PARAMETER | TYPE | DESCRIPTION
--- | --- | ---
header | string | The default header to be added
value | string | The value to set the header to

## api.SetHeader( header, value )
Used to modify a default API header

PARAMETER | TYPE | DESCRIPTION
--- | --- | ---
header | string | The default header to be modified
value | string | The value to set the header to

## api.RemoveHeader( header )
Used to remove a default API header

PARAMETER | TYPE | DESCRIPTION
--- | --- | ---
header | string | The default header to be removed
