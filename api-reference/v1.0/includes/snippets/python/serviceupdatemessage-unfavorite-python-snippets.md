---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(request_adapter)

request_body = UnfavoritePostRequestBody(
	message_ids = [
		"MC172851",
		"MC167983",
	]
)

result = await graph_client.admin.service_announcement.messages.unfavorite.post(request_body = request_body)


```