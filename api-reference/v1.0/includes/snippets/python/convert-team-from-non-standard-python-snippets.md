---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(request_adapter)

request_body = Team(
	display_name = "My Class Team",
	description = "My Class Team’s Description",
	additional_data = {
			"template@odata_bind" : "https://graph.microsoft.com/v1.0/teamsTemplates('educationClass')",
	}
)

result = await graph_client.teams.post(request_body = request_body)


```