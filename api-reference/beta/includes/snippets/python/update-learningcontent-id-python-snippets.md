---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(request_adapter)

request_body = LearningContent(
	title = "Manage classes, resources, assessment, and planning in Microsoft Teams with Beedle",
	description = "A module to guide users through the various teaching and learning enhancements that Beedle provides within Microsoft Teams, with many examples of everyday application.",
	content_web_url = "https://learn.microsoft.com/learn/modules/manage-classes-resources-assessment-planning-beedle/",
	source_name = "MsLearn",
	thumbnail_web_url = "https://syndetics.com/index.aspx?isbn=9783319672175/LC.GIF",
	language_tag = "en-us",
	number_of_pages = 9,
	duration = "PT20M",
	format = "Book",
	created_date_time = "2018-01-01T00:00:00Z",
	last_modified_date_time = "2021-04-01T04:26:06.1995367Z",
	contributors = [
		"Scott Simpson",
	]
	additional_tags = [
		"Create private or public teams",
		"Add members to teams",
	]
	skill_tags = [
		"Create teams",
		"Teams channels",
		"Teams members",
	]
	is_active = True,
	is_premium = False,
	is_searchable = True,
)

result = await graph_client.employee_experience.learning_providers.by_learning_provider_id('learningProvider-id').learning_contents.by_learning_content_id('learningContent-id').patch(request_body = request_body)


```