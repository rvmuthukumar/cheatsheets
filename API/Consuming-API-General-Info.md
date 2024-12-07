

## How to Work When receiving Data
- We make Requests to the API server 
- it responds with data & response code
- Consult API Docs For:
    - Successful API Requests
    - API end points - often they are multiple
    - Query Parameters are optional and can help minimize the subset of data retrieved 
    - Auth method
    - Expected Response Format 
        - they may be of xml, JSON
    - Typical documentation would like this example
        - Endpoint: /weather
        - Method: GET
            - Query Parameters:
            - city (required): Name of the city
            - units: Measurement units (metric or imperial)
        - Response: JSON object containing weather details

## Query Parameters
- Query Parameters are added to the URL of an API request
- syntax
    - `?` followed by the query parameters
    - example `https://api.example.com/data?parameter1=value1&parameter2=value2`
- Use cases
    - Filtering data
    - Sorting Data
    - Pagination - to limit the no of data rows in a single request
    - Search
    - Configuring Responses
    


## Common API Status Codes
- Complete list of status code can be found at https://developer.mozilla.org/en-US/docs/Web/HTTP/Status
- All OK (2XX)
    - 200: Everything went okay, and the result has been returned (if any).
- Something Wrong But Managed (3XX)
    - 301: The server is redirecting you to a different endpoint. This can happen when a company switches domain names, or an endpoint name is changed.
- Something is Wrong Due To Client Side Issues (4XX)
    - 400: The server thinks you made a bad request. This happens when you send incorrect data or make other client-side errors.
    - 401: The server thinks you're not authenticated. Many APIs require login credentials, so this happens when you don't send the right credentials to access an API.
    - 403: The resource you're trying to access is forbidden: you don't have the right permissions to see it.
    - 404: The resource you tried to access wasn't found on the server.
- Something Went Wrong On The Server Side (5XX)
    - 503: The server is not ready to handle the request.


## Python Code Structure
- We need to use python modules like;
    - requests for synchronous http request. https://requests.readthedocs.io/en/latest/
    - HTTPx Same as Requests but with async capability http client 

- `pip install requests`
- `import requests`
- `response=requests.get("URLAddress)`
- `print(response.status_code)`
- `json.dumps(obj,sort_keys=True, indent=4)` # takes in a Python JSON obj and converts to string
- `json.loads()` # Takes a JSON string and converts to a python JSON object


## Tips
- Navigate doc carefully
    - Check how Auth is handled. API KEys are OAuth - use of incorrect auth may result in 401 error
    - Understand rate limits if any
    - Check end points methods
    - Review request and response formats
    - look for examples