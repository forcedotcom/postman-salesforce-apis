# Salesforce Postman Collection
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

<img alt="Postman screenshot" src="/doc-resources/postman-screenshot.jpg" width="600"/>

# Installation

1. Download the [latest Postman collection](https://github.com/scolladon/Salesforce-Postman/releases/latest/download/salesforce-apis.postman_export.json) or go to [previous releases](https://github.com/scolladon/Salesforce-Postman/releases). The collection comes as a `salesforce-apis.postman_export.json` file.

1. [Import it in Postman](https://learning.postman.com/docs/postman/collections/data-formats/#importing-postman-data).

# Usage

1. Clone the "Salesforce Template" Postman environment. Never customize the template directly! Always clone it and link the environment created to the target Sandbox, Trailhead Playground (TP), Developer Edition (DE) or production org.
1. Edit the environment and fill in these variables:
    - url (login, test or mydomain)
    - username
    - password (+ security token if required)
1. Use your preferred authentication method (SOAP login is very convenient). This automatically fills the endpoint url and access token environment variables for subsequent API calls.
1. Use any of the API endpoints from the collection.<br/>
  **Note:** some APIs are just boilerplates (ex : UI API), you need to copy them and customize them (uri + get parameters) according to your need.

# Contributions

## Prerequisites

Install the following apps:
- [Postman](https://learning.postman.com/docs/postman/launching-postman/installation-and-updates/) installed on your laptop.
- [Postman Extractor](https://github.com/pozil/postman-extractor).

## Development Lifecycle

1. Install the library in your Postman in a new dedicated workspace.

1. Develop new APIs directly in Postman.

1. Export the collection using the [export data feature](https://learning.postman.com/docs/postman/collections/data-formats/#data-dumps).

1. Use [Postman Extractor](https://github.com/pozil/postman-extractor) to format the collection for easier versioning:
    ```bash
    $ pmx import -f Backup.postman_dump.json
    ```
1. Commit **only** the result of the import command.
    
    **/!\ Never commit credentials!**

1. Verify that the packaging is correct by exporting it to JSON:
    ```bash
    $ pmx export -o export.salesforce-postman.json
    ```
    and [reimporting](https://learning.postman.com/docs/postman/collections/data-formats/#importing-postman-data) it in Postman.
    If everything goes well and the API you've developed are there and other APIs are not missing you're probably good.

## Coding Conventions

Stage only what is relevant to what you've done

### Branch Naming Conventions

Follow these naming conventions for branches:
- new feature: `feature/feature-name`
- fix: `fix/fix-name`

### API Development

Follow these rules:
- Only one folder per API, no sub folders
- Use the API documentated names
- Add description from the documentation into the Postman descriptions
- Provide the description from the documentation for each GET parameters
- API calls should work and be parametrized using environment variables
- Optional: provide examples

### PR Checks

For each Pull Request we'll check those items:
- [X] No conflict
- [X] No credentials in sources
- [X] Successful export of the Postman collection into JSON format
- [X] Successful import of the JSON file into Postman collection

### PR Results

Upon merging a PR in master we'll create a new release.
New release versions follow the [semver convention](https://semver.org/).
