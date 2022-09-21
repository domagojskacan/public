# public
task1 


Implement an HTTP service that accepts the upload of user data serialized in one of csv, json or yaml format, parses the data, and stores them as files in all three mentioned formats to a directory that collects all files for given user where user is identified by arbitrary id that is a part of endpoint route. The filename should also be part of the endpoint route. After files are stored, the data can be fetched in any of the defined serialization formats. User should also have an option to delete one or all uploaded files.

Things to consider:

User data is always structured flat and the key is string, while the value is any primitive type,

Incoming data serialization format (upload) and outgoing data serialization format (download) is determined by HTTP header,

If a user tries to overwrite the file (already exists), return error,

Service must support graceful shutdown with a timeout (a minute for example).




task2 


Enable user login via static HTML web page that is asking for username and password (Note: Don't spend time on design, plain HTML form is good enough)
Store username and password in RDBMS of your choice, preferably something lightweight like sqlite, etc. (Note: Consider security best practices in storing user's password),
Upon successful login, generate an access token, store it in Redis (with defined TTL) and display the access token and corresponding TTL on the web page,
For any file operation: Authentication middleware that uses standard Bearer authorization header,
In this task, starting Redis, creating DB, creating DB table, and inserting a couple of test users should be done with bash startup script prior to starting the service (Note: Start redis as a docker to simplify setup).
