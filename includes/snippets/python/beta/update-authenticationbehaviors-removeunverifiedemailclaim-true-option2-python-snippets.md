---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(request_adapter)

request_body = Application(
	authentication_behaviors = AuthenticationBehaviors(
		remove_unverified_email_claim = True,
	),
)

result = await graph_client.applications.by_application_id('application-id').patch(request_body = request_body)


```