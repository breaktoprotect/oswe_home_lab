# Preparing Home Lab for OSWE
## Description
Tips &amp; Tricks &amp; Troubleshooting to prepare study lab for OSWE. This is useful for OffSec students who wants to build similar labs for OSWE after their initial AWAE lab availability period. Although home lab is inexpensive, it may not always be straight forward. A lot of work has been put into preparing the AWAE labs thus the cost of renting them is not cheap. However, this advisory seeks to help out OffSec students to overcome certain issues that they may face. 

# Bassmaster@1.5.1 Installation
## Windows steps
1. Install NodeJS version 8.* (may not be necessary, but do this if your initial installation fails)
2. Create a directory just for your lab experiment (e.g. mod5_bassmaster)
3. Within the directory, install bassmaster v1.5.1:
`npm install bassmaster@1.5.1`
4. Followed by hapi version 12:
`npm isntall hapi@12`
5. Your example\batch.js would probably not work at this point. You need the latest bassmaster's batch.js.
  a. Create a new directory.
  b. Then: `npm install bassmaster`
  c. Go into node_modules\bassmaster\examples\
  d. Copy the batch.js file and overwrite your bassmaster v1.5.1 examples\batch.js
  e. If port 8080 is used by your Burpsuite, go into the batch.js edit the following line to your preferred listening port:
  `    internals.http.connection({ port: 8080 });`
6. Go back to your lab experiment directory and into the bassmaster v1.5.1, run the following command:
```node examples\batch.js```
7. Browse to the 'request' URI on the host at the port you have set, for example:
`http://localhost:8000/request'
8. You should observe a JSON response such as:
```json
[{"id":"fa0dbda9b1b","name":"John Doe"},{"id":"55cf687663","name":"Active Item"},{"id":"55cf687663","name":"Item"}]
```
