---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(request_adapter)

request_body = AccessPackageAssignmentPolicy(
	display_name = "extension-policy",
	description = "test",
	access_package_id = "ba5807c7-2aa9-4c8a-907e-4a17ee587500",
	can_extend = False,
	request_approval_settings = None,
	requestor_settings = RequestorSettings(
		accept_requests = True,
		scope_type = "AllExistingDirectorySubjects",
		allowed_requestors = [
		]
		additional_data = {
				"is_on_behalf_allowed" : False,
		}
	),
	access_review_settings = None,
	questions = [
	]
	custom_extension_stage_settings = [
		CustomExtensionStageSetting(
			stage = AccessPackageCustomExtensionStage.AssignmentRequestCreated,
			custom_extension = CustomCalloutExtension(
				id = "219f57b6-7983-45a1-be01-2c228b7a43f8",
			),
		),
		CustomExtensionStageSetting(
			stage = AccessPackageCustomExtensionStage.AssignmentRequestGranted,
			custom_extension = CustomCalloutExtension(
				id = "219f57b6-7983-45a1-be01-2c228b7a43f8",
			),
		),
	]
	additional_data = {
			"expiration" : (
				type = "afterDuration",
				duration = "P365D",
			),
	}
)

result = await graph_client.identity_governance.entitlement_management.acces_package_assignment_policies.post(request_body = request_body)


```