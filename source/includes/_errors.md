# Errors

<aside class="notice">
The most common errors on this site are when users exceed their rate limit, or when users provide the wrong API Keys (errors 429 and 403 respectively). If you continue to run into issues accessing the API, please contact us.
</aside>

The Bitformance API uses the following error codes:


Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request is invalid.
403 | Forbidden -- The API keys in the request were invalid.
404 | Not Found -- The specified endpoint could not be found.
429 | Too Many Requests -- You have exceeded your API Key's rate limit according to its tier.
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.
