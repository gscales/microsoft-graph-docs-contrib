---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(request_adapter)

request_body = Calendar(
	name = "Volunteer",
)

result = await graph_client.me.calendars.post(request_body = request_body)


```