# Geolocation

Note: Javascript used to get Geo Data. Pick API services that can give the data your project need.

## Getting Basic Geolocation Data

Use the new HTML5 Geolocation API to get the user’s location.

The navigator object gives us access to the new geolocation object. The geolocation object has the following methods.

- getCurrentPosition() returns the user’s current position.
- watchPosition() returns the user’s current position, but also continues to monitor the position and invoke the appropriate callback every time the position changes.
- clearWatch() ends the watchPosition() method’s monitoring of the current position.

When determining the location of the Internet device, first check that the user’s browser supports the Geolocation feature natively.

If it does, call the getCurrentPosition() method.

    if (navigator && navigator.geolocation) {
        navigator.geolocation.getCurrentPosition(geo_success, geo_error);
    } else {
        error('Geolocation is not supported.');
    }

Since this method executes asynchronously, pass it two callback functions. geo_success and geo_error.

The error callback is passed a position error object that contains a code and a message property.

The code can be one of the following:

1. Unknown
2. Permission Denied
3. Position Unavailable
4. Timeout

The success callback is passed a position object that contains a coordinates object and a timestamp. The coordinates object contains the following.

- latitude , which is specified in decimal degres
- longitude , which is specified in decimal degrees
- altitude , which is specified in meters above the ellipsoid
- accuracy , which is specified in meters
- altitudeAccuracy , which is specified in meters
- heading , which is the direction of travel specified in degrees
- speed , which is specified in meters per second

Of those seven, only three are guaranteed to be there: latitude , longitude , and accuracy.

## Convert latitude and longitude into address

The Geocoder object gives us access to the geocode() method, which can take in a variety of options and return information based on them.

Pass Latitude and Longitude in GeoCode() to get Address.

## Convert address into latitude and longitude coordinates

In order to do so, call the geocode() method, but pass an address option instead of latitude and longitude.

Then access the geometry property of the GeocoderResults object. The geometry property contains a location property that can then be used to call the lat and lng methods to get our address’s coordinates.
