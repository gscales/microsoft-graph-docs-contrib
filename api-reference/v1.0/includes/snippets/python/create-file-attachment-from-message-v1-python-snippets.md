---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(request_adapter)

request_body = FileAttachment(
	odata_type = "#microsoft.graph.fileAttachment",
	name = "smile",
	content_bytes = base64.urlsafe_b64decode("R0lGODdhEAYEAA7"),
)

result = await graph_client.me.messages.by_message_id('message-id').attachments.post(request_body = request_body)


```