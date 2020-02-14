# Salesforce APIs for Postman
A collection of [Postman](https://www.postman.com/) resources for the Salesforce APIs:

![Postman screenshot](/doc-resources/postman-screenshot.jpg)

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

# Postman Architecture
## Template Environnement

Salesforce template environment meant to be duplicated for each of your environment. Do not modify it directly
Environment variable have been designed to be used by the API endpoint in order to :
- Store values from call result (access token, job id, refresh token, etc)
- Use values as variable in call (url, endpoint, access token, username, password, etc)
Postman "Tests" feature is used to parse query result and store environment variables

## Salesforce Preset

Predefine header presets meant to be used when creating new API from scratch.
Allow to have the Authorization header prefilled with the right syntax and environment variable
Use it when you need to create a new API call from scratch.

## Salesforce Collection

Salesforce APIs Postman Collection
Name of the endpoint and its description are taken from the Salesforce documentations.
Collections use environment variable in order to partition the variable content per env and easily switch between environment

### APIs in the box
- Auth
- Bulk (V1 & V2)
- Async Query
- Rest
- UI 
- Tooling
- Metadata
- Composite
- Chatter

# Contributions

[Contribution guidelines for this project](CONTRIBUTE.md)