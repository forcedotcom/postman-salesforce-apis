# Prerequisites

Install the following apps:
- [Postman](https://learning.postman.com/docs/postman/launching-postman/installation-and-updates/)
- [Postman Extractor](https://github.com/pozil/postman-extractor)

# Development Lifecycle

1. Install the library in your Postman in a new dedicated workspace.

1. Develop new APIs directly in Postman.

1. Export the entire Postman workspace using the [export data feature](https://learning.postman.com/docs/postman/collections/data-formats/#data-dumps).

1. Use [Postman Extractor](https://github.com/pozil/postman-extractor) to format the collection for easier versioning:
    ```bash
    $ pmx import -f Backup.postman_dump.json
    ```

1. Remove unneeded files (the JSON dump file, other collections, other environments...)

1. Check your files for hardcoded Ids or credentials
    
    **/!\ Never commit credentials!**

1. Verify that the packaging is correct by exporting it to JSON:
    ```bash
    $ pmx export -o export.salesforce-postman.json
    ```
    and [reimporting](https://learning.postman.com/docs/postman/collections/data-formats/#importing-postman-data) it in Postman.
    If everything goes well and the API you've developed are there and other APIs are not missing you're probably good.

# Coding Conventions

Stage only what is relevant to what you've done

## Branch Naming Conventions

Follow these naming conventions for branches:
- new feature: `feature/feature-name`
- fix: `fix/fix-name`

## API Development

Follow these rules:
- Only one folder per API, no sub folders
- Use the API documentated names
- Add description from the documentation into the Postman descriptions
- Provide the description from the documentation for each GET parameters
- API calls should work and be parametrized using environment variables
- Optional: provide examples

## PR Checks

For each Pull Request we'll check those items:
- [X] No conflict
- [X] No credentials in sources
- [X] Successful export of the Postman collection into JSON format
- [X] Successful import of the JSON file into Postman collection

## PR Results

Upon merging a PR in master we'll create a new release.
New release versions follow the [semver convention](https://semver.org/).
