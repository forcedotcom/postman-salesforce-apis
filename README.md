# Salesforce-Postman
Salesforce API Postman Collection

# How to install it

Go to the [release section](https://github.com/scolladon/Salesforce-Postman/releases) to download the salesforce-apis.postman_export.json from the release you want.

[Import](https://learning.postman.com/docs/postman/collections/data-formats/#importing-postman-data) it into postman

# How to contribute
## Prerequisite
You need to have installed :
- [Postman](https://learning.postman.com/docs/postman/launching-postman/installation-and-updates/).
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
Add the description from the documentation into the description
Provide the description from the documentaton for each parameter
Optional: provide examples

### PR Checks
Each Pull request will check those item :
- [X] No conflict
- [X] Successful Export of the files into json file
- [X] Successful Importing of the json file into Postman
### PR Result
New release following semver convention will be created to include new fonctionalities
