# weatherapi

Objective :-
 waether API will display local weather for  offices/locations of Rocket Group on an internal company site. This API would need to take an IP address as an
input and return weather information for the a matching location.

## Description :-

API takes input ipaddress as query paramter and performs 3 core tasks on High level
  - Geo-code the receive ip address to find out postalcode/zipcode.                                                                                                                 
  - check if the zipcode is from pre-defined location list.
  - get the weather info of zipcode
  
Following public APIs are utilized by weather API


- api.zip-codes.com --> to get list of zipcode of a state
- api.weatherapi.com --> to get weather of give zipcode
- ip-api.com --> to geo-code ip address

## API Endpoints

- /weatherinfo : This is primary endpoint to get weather Information.
- /syncdrive : This endpoint provides capability to Manually sync LocationList from to object store in addition to predefined scehduler
- /inspect : This endpoint provides capability to inspect internally Maintained LocationList
- /apiheartbeat: endpoint to check availbility status of API

 ### Public API endpoints
 
- https://weatherapimpl.us-e2.cloudhub.io/googledriveauthorize
- https://weatherapimpl.us-e2.cloudhub.io/api/weatherinfo/apiheartbeat
- https://weatherapimpl.us-e2.cloudhub.io/api/weatherinfo/syncdrive
- https://weatherapimpl.us-e2.cloudhub.io/api/weatherinfo/inspect
- https://weatherapimpl.us-e2.cloudhub.io/api/weatherinfo?ipaddress=2601:647:6400:5f60:145b:fa0f:bd5b:ea8c

## API Features

### Security

- Https endpoints: To enhnace security, API utilized keystore file to expose https endpoints.
- Encryption : sensitive properties are encrypted using secure-property plugin
