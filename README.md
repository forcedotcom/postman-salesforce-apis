> ℹ️  **January 2021 update:** the collection sources were moved to the Postman API Network.<br/>
This repository will continue to host the documentation and track issues.


# Salesforce APIs for Postman

A [Postman](https://www.postman.com) collection of 230+ requests for the following Salesforce APIs:

<table>
   <tr>
      <td>
         <ul>
            <li>Async Query</li>
            <li>Auth</li>
            <li>Bulk (V1 & V2)</li>
            <li>Chatter (Connect)</li>
            <li>Composite</li>
         </ul>
      </td>
      <td>
         <ul>
            <li>CPQ</li>
            <li>Metadata</li>
            <li>Rest</li>
            <li>Tooling</li>
            <li>UI</li>
         </ul>
      </td>
   </tr>
</table>

![Postman screenshot](doc-gfx/app/limits-status-200.png)

Learn more about the Collection:
- 🎥 [Webinar](https://trailhead.salesforce.com/live/videos/a2r3k000001WFhk/exploring-the-salesforce-apis-with-postman/)
- 📖 [Blog post](https://developer.salesforce.com/blogs/2020/03/explore-the-salesforce-apis-with-a-postman-collection.html)

**⚠️ Disclaimers:**
- This collection is provided as-is. It's not officially supported by Salesforce or covered by SLAs.
- API documentation is not provided with the collection. Please refer to the [official documentation](https://developer.salesforce.com/docs).

## Issues and Questions

Report issues and ask questions [here](https://github.com/forcedotcom/postman-salesforce-apis/issues).

## Installation

You can use the **Postman desktop app** or the **Postman web UI** to connect to Salesforce with the Salesforce APIs collection. Use the following table to decide which option works best for you:

| Installation Option	| Pros	| Cons	|
| ---	| ---	| ---	|
| [Option 1: Using Postman Desktop App (Recommended)](install-api-network-app.md)	| - **Fast setup** (approx. 10 minutes)<br/>- No changes required in Salesforce<br/>- Supports all authentication methods	|	|
| [Option 2: Using Postman Web UI](install-api-network-web.md)	| - **No software installation required**	| - **Longer setup** (approx. 20 minutes) with greater risk of configuration error<br/>- **Requires Salesforce Org configuration**<br/>- Limited support for authentication methods due to CORS browser restrictions	|

Regardless of whether you choose the desktop app or the web UI, you can use all of the collection’s requests and your changes are synchronized between the two environments so you can easily switch between them at any time.


## Variables Reference

The collection comes with some collection variables but we recommend overriding these variables by working with clones of the [Salesforce Template Environment](https://www.postman.com/salesforce-developers/workspace/salesforce-developers/environment/12721794-8b74caf1-3cbb-44d0-b245-855c0fb25f0d). Using environments lets you connect to multiple orgs in parallel.

The collection relies on the following variables:

| Variable | Description |
| --- | --- |
| `url` | The base URL for all requests. Either:<br/>- `https://test.salesforce.com` for sandboxes or Scratch orgs<br/>- `https://login.salesforce.com` for production, Trailhead Playground and Developer Edition orgs<br/>- your custom My Domain base URL. |
| `version` | The Salesforce API version (e.g.: 50.0). |
| `username ` | Your username. |
| `password ` | Your password. |
| `secretToken ` | Your personal [security token](https://help.salesforce.com/articleView?id=user_security_token.htm). |
| `clientId ` | Connected App client Id. |
| `clientSecret ` | Connected App client secret. |
| `redirectUrl ` | Connected App redirect URL for OAuth 2.0. |
| `initAccessToken ` | Initial access token for dynamic Connected App registration. |
| `site ` | Community suffix when connecting with an Experience Cloud user. |

Only a few of these variables are mandatory. The authentication requests will automatically register and set extra "private" variables identified with a `_` prefix (e.g.: `_accessToken`, `_endpoint`, `_orgId`, `_userId`...).


## Contributing

Follow [these instructions](contributing.md) to contribute to the collection.
