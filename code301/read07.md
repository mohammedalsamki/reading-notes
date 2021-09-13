# Autocomplete
Provides options for user input by understanding it on-the-fly, returning matches as a dropdown.

Can match on full words as well as substrings
Plugins for easy implementation

## Nearby
Returns specified Points of Interests (Fuel pumps, ATMs, Restaurants, etc) or Places around a given coordinate.

## 
Affordable, Scalable & Reliable location services since 2013. We proudly serve 100k+ developers who make 2 billion+ requests each day.

## /businesses/search
This endpoint returns up to 1000 businesses based on the provided search criteria. It has some basic information about the business. To get detailed information and reviews, please use the Business ID returned here and refer to /businesses/{id} and /businesses/{id}/reviews endpoints.

Note: at this time, the API does not return businesses without any reviews.

Request
GET https://api.yelp.com/v3/businesses/search
Parameters
These parameters should be in the query string.

Name	Type	Description
term	string	Optional. Search term, for example "food" or "restaurants". The term may also be business names, such as "Starbucks". If term is not included the endpoint will default to searching across businesses from a small number of popular categories.
location	string	Required if either latitude or longitude is not provided. This string indicates the geographic area to be used when searching for businesses. Examples: "New York City", "NYC", "350 5th Ave, New York, NY 10118". Businesses returned in the response may not be strictly within the specified location.
latitude	decimal	Required if location is not provided. Latitude of the location you want to search nearby.
longitude	decimal	Required if location is not provided. Longitude of the location you want to search nearby.
radius	int	Optional. A suggested search radius in meters. This field is used as a suggestion to the search. The actual search radius may be lower than the suggested radius in dense urban areas, and higher in regions of less business density. If the specified value is too large, a AREA_TOO_LARGE error may be returned. The max value is 40000 meters (about 25 miles).
categories	string	Optional. Categories to filter the search results with. See the list of supported categories. The category filter can be a list of comma delimited categories. For example, "bars,french" will filter by Bars OR French. The category identifier should be used (for example "discgolf", not "Disc Golf").
locale	string	Optional. Specify the locale into which to localize the business information. See the list of supported locales. Defaults to en_US.
limit	int	Optional. Number of business results to return. By default, it will return 20. Maximum is 50.
offset	int	Optional. Offset the list of returned business results by this amount.
sort_by	string	Optional. Suggestion to the search algorithm that the results be sorted by one of the these modes: best_match, rating, review_count or distance. The default is best_match. Note that specifying the sort_by is a suggestion (not strictly enforced) to Yelp's search, which considers multiple input parameters to return the most relevant results. For example, the rating sort is not strictly sorted by the rating value, but by an adjusted rating value that takes into account the number of ratings, similar to a Bayesian average. This is to prevent skewing results to businesses with a single review.
price	string	Optional. Pricing levels to filter the search result with: 1 = $, 2 = $$, 3 = $$$, 4 = $$$$. The price filter can be a list of comma delimited pricing levels. For example, "1, 2, 3" will filter the results to show the ones that are $, $$, or $$$.
open_now	boolean	Optional. Default to false. When set to true, only return the businesses open now. Notice that open_at and open_now cannot be used together.
open_at	int	Optional. An integer represending the Unix time in the same timezone of the search location. If specified, it will return business open at the given time. Notice that open_at and open_now cannot be used together.
attributes	string	Optional. Try these additional filters to return specific search results!
hot_and_new - popular businesses which recently joined Yelp
request_a_quote - businesses which actively reply to Request a Quote inquiries
reservation - businesses with Yelp Reservations bookings enabled on their profile page
waitlist_reservation - businesses with Yelp Waitlist bookings enabled on their profile screen (iOS/Android)
deals - businesses offering Yelp Deals on their profile page
gender_neutral_restrooms - businesses which provide gender neutral restrooms
open_to_all - businesses which are Open To All
wheelchair_accessible - businesses which are Wheelchair Accessible
You can combine multiple attributes by providing a comma separated like "attribute1,attribute2". If multiple attributes are used, only businesses that satisfy ALL attributes will be returned in search results. For example, the attributes "hot_and_new,request_a_quote" will return businesses that are Hot and New AND offer Request a Quote.
