## Creating an API client in Trelica

Please review [https://help.trelica.com/hc/en-us/articles/7739284192413-Creating-an-app](this article).

## QRadar Log Source Configuration

1. Log in to QRadar.
2. Under _Admin_ > _DSM Editor_, create a new DSM for "Trelica". Save and exit.
3. Under _Admin_ > _QRadar Log Source Management_, create a new single Log Source with the following arttibutes.
- Log Source Type = Trelica
- Protocol Type = Universal Cloud REST API
- Coalescing Events = No
- Log Source Identifier = app.trelica.com
- Workflow = <<< Copy and paste [Trelica-Workflow.xml](Trelica-Workflow.xml) unchanged >>>
- Workflow Parameter Values = <<< Copy and paste [Trelica-Workflow-Parameter-Values.xml](Trelica-Workflow-Parameter-Values.xml), updating client_id/client_secret with the API values obtained from Trelica > Admin > Settings > API >>>
- Recurrence = 6H
4. In the Test protocol parameters window, click _Start Test_.
5. Click _Finish_ and deploy the changes (Deploy Changes -> Advanced -> Deploy Full Configuration)