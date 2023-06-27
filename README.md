## Creating an API client in Trelica

You can create an API client in Trelica by going to **Admin** > **Settings** > **API**.

Use client credentials, and ensure the `Audit log` scope is selected for the client.

Please review [this article](https://help.trelica.com/hc/en-us/articles/7739284192413-Creating-an-app) for more information.

## QRadar Log Source Configuration

1. Log in to QRadar.
2. Go to **Admin** > **DSM Editor**, create a new DSM called `Trelica`. Save and exit.
3. Under **Admin** > **QRadar Log Source Management**, create a new single Log Source with the following attributes:
- Log Source Type = `Trelica`
- Protocol Type = `Universal Cloud REST API`
- Coalescing Events = `No`
- Log Source Identifier = `app.trelica.com`
- Workflow = <<< Copy and paste [Trelica-Workflow.xml](Trelica-Workflow.xml) unchanged >>>
- Workflow Parameter Values = <<< Copy and paste [Trelica-Workflow-Parameter-Values.xml](Trelica-Workflow-Parameter-Values.xml), updating `client_id` and `client_secret` with the API values obtained from Trelica. >>>
- Recurrence = `6H`
4. In the **Test protocol parameters** window, click **Start Test**.
5. Click **Finish**.
6. Deploy the changes by going to **Deploy Changes** > **Advanced** > **Deploy Full Configuration**.
