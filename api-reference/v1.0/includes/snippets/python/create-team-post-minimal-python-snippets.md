---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(request_adapter)

request_body = Team(
	display_name = "My Sample Team",
	description = "My Sample Team’s Description",
	members = [
		AadUserConversationMember(
			odata_type = "#microsoft.graph.aadUserConversationMember",
			roles = [
				"owner",
			]
			additional_data = {
					"user@odata_bind" : "https://graph.microsoft.com/v1.0/users('0040b377-61d8-43db-94f5-81374122dc7e')",
			}
		),
	]
	additional_data = {
			"template@odata_bind" : "https://graph.microsoft.com/v1.0/teamsTemplates('standard')",
	}
)

result = await graph_client.teams.post(request_body = request_body)


```