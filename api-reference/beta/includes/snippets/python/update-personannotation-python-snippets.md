---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(request_adapter)

request_body = PersonAnnotation(
	allowed_audiences = AllowedAudiences.Organization,
)

result = await graph_client.users.by_user_id('user-id').profile.notes.by_note_id('personAnnotation-id').patch(request_body = request_body)


```