---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(request_adapter)

request_body = MeetingRegistrant(
	odata_type = "#microsoft.graph.meetingRegistrant",
	first_name = "Frederick",
	last_name = "Cormier",
	email = "frederick.cormier@contoso.com",
	custom_question_answers = [
		CustomQuestionAnswer(
			question_id = "MSM5YjlmM2Q4ZS03ZmVkLTRmN3gwMDIw94MDAyMF9hX3gwMDIwX2RldmU=",
			value = "No",
		),
		CustomQuestionAnswer(
			question_id = "MSM5M2E2OWQ1Ni1jZTc4LTQDAwMjBfZGlkX3gwMDIwX3lvdV94MDAyMF8=",
			value = "Internet",
		),
	]
)

result = await graph_client.users.by_user_id('user-id').online_meetings.by_online_meeting_id('onlineMeeting-id').registration.registrants.post(request_body = request_body)


```