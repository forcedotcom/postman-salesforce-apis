[Back to main page](README.md)

# Working with environments to connect to multiple Salesforce orgs

You can use the Postman desktop app with environments to work with multiple Salesforce orgs in parallel.

> ⚠️ Using environments means that you will store Salesforce credentials in clear in Postman. Do this at your own risks.


- [Import the Template Environment](#import-the-template-environment)
- [Configure the Environment](#configure-the-environment)
- [Change the Collection Authorization Type](#change-the-collection-authorization-type)
- [Authenticate with Salesforce](#authenticate-with-salesforce)


## Import the Template Environment

1. Using a browser, [sign up/in to Postman](https://identity.getpostman.com/login).
1. Open the main collection with [this link](https://www.postman.com/salesforce-developers/workspace/salesforce-developers).
1. Select the **Environments** tab (item A in following screenshot)
1. Click **Salesforce Environment Template** (B)
1. Click on the “three dots” icon on the right (C) and select **Export** from the menu.

    ![Export environment screenshot](doc-gfx/web/export-env.png)

    This downloads a `Salesforce Template Environment.postman_environment.json` file.

1. Close the browser tab. We'll continue the installation on the Postman app.
1. In the Postman app, click **Import**.
1. Drag and drop the JSON file you just downloaded in the gray zone.
1. Click **Import**.


## Configure the Environment

1. Click on the Manage Environment icon

    ![Manage environment screenshot](doc-gfx/app/manage-env.png)

1. Click on the Duplicate Environment icon next to the Salesforce Template Environment

    ![Duplicate environment screenshot](doc-gfx/app/duplicate-env.png)

    This creates a `Salesforce Environment Template Copy` template.

1. Click **Salesforce Environment Template Copy**.
1. Rename the environment with something meaningful in relation with your Salesforce org (e.g.: “Playground 1”).
1. Set values in the CURRENT VALUE column for the following variables:

    | Variable	| Current Value	|
    | ---	| ---	|
    | `url`	| Either:<br/>- `https://test.salesforce.com` for sandboxes or Scratch orgs.<br/>- `https://login.salesforce.com` for production, Trailhead Playground and Developer Edition orgs.<br/>- your custom My Domain URL.	|
    | `username`	| Your username	|
    | `password`	| Your password	|
    | `secretToken`	| Your personal [security token](https://help.salesforce.com/articleView?id=user_security_token.htm) (if required by your org)	|

1. Click **Update** and close the environments dialog.
1. Select your environment from the environment dropdown.

    ![Select environment screenshot](doc-gfx/app/select-env.png)


## Change the Collection Authorization Type

1. Move your mouse over the “Salesforce APIs” collection, click on the “three dots” icon next to it and select **Edit** from the menu.

    ![Edit collection screenshot](doc-gfx/app/edit-collection.png)

1. In the **Authorization** tab, select **Bearer Token** as the authorization type.
1. Enter `{{_accessToken}}` for the Token value.
1. Click **Update**


## Authenticate with Salesforce

1. Open the collection’s **Auth** folder and select the **SOAP Login** request
1. Click **Send**

At this point, if your environment is correctly set up, you should see a `200 OK` status. This means that you have successfully authenticated with Salesforce and that you can now use the other collection’s requests.

![Authenticate screenshot](doc-gfx/app/soap-login-status-200.png)


[Back to main page](README.md)
