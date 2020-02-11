# Salesforce-Postman
A collection of [Postman](https://www.postman.com/) resources for the Salesforce APIs:
- Auth
- Bulk (V1 & V2)
- Async Query
- Rest
- UI 
- Tooling
- Metadata
- Composite
- Chatter

# How to install it

Latest salesforce-apis.postman_export.json [here](https://github.com/scolladon/Salesforce-Postman/releases/latest/download/salesforce-apis.postman_export.json).
Or go to the [release section](https://github.com/scolladon/Salesforce-Postman/releases) to download the salesforce-apis.postman_export.json from the release you want.

[Import](https://learning.postman.com/docs/postman/collections/data-formats/#importing-postman-data) it into postman

# How to use it
## Configuring the environment
Clone the "Salesforce Template" environment. Never customize the template !! Always clone to link the environment created to the target sandbox/trailhead playground/developer org/production
Fill the url (login, test, mydomain), username, password (+ security token if required) variable for this new environment
## Authenticating
Use your preferred authentication method (SOAP login is very convenient) to get endpoint url and access token environment variable filled for you
## Calling an API endpoint
Use the API you need from the collection.
Some APIs are just boilerplate preconfigured (ex : UI API), you will need to copy it and customize it (uri + get parameters) according to your need.

# How to contribute
## Prerequisite

- [Postman](https://learning.postman.com/docs/postman/launching-postman/installation-and-updates/) installed on your laptop.
- [Postman Extractor](https://github.com/pozil/postman-extractor).

## Development Lifecycle

First of all install the library in your postman in a new workspace dedicated to it.

Develop new API directly in your Postman

Export the development using the [export data feature](https://learning.postman.com/docs/postman/collections/data-formats/#data-dumps)

Use [Postman Extractor](https://github.com/pozil/postman-extractor) to create metadata :
```bash
$ pmx import -f Backup.postman_dump.json
```
Commit **only** the result of the import command
/!\ never commit credential !

In order to verify the packaging is correct export it to json
```bash
$ pmx export -o export.salesforce-postman.json
```
and [reimport](https://learning.postman.com/docs/postman/collections/data-formats/#importing-postman-data) it in Postman.
If everything goes well and the API you've developed are there and other APIs are not missing you're probably good.

## Coding Convention

Stage only what is relevant to what you've done

### Branch naming convention
For the repository and create feature branch per feature/fix you want to implement :
- feature : feature/*feature name*
- fix : fix/*fix name*

### API Development
Only one folder per API, no sub folders
For each API call, use the documentation name of the API
Add the description from the documentation into the postman description
Provide the description from the documentaton for each GET parameters
API call should work and be parametrized using environment variable
Optional: provide examples

### PR Checks
Each Pull request will check those item :
- [X] No conflict
- [X] No credential in sources
- [X] Successful Export of the files into json file
- [X] Successful Importing of the json file into Postman
### PR Result
New release following semver convention will be created to include new fonctionalities
