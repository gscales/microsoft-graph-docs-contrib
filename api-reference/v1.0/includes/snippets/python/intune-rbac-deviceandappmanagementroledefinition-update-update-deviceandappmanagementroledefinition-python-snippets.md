---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(request_adapter)

request_body = DeviceAndAppManagementRoleDefinition(
	odata_type = "#microsoft.graph.deviceAndAppManagementRoleDefinition",
	display_name = "Display Name value",
	description = "Description value",
	role_permissions = [
		RolePermission(
			odata_type = "microsoft.graph.rolePermission",
			resource_actions = [
				ResourceAction(
					odata_type = "microsoft.graph.resourceAction",
					allowed_resource_actions = [
						"Allowed Resource Actions value",
					]
					not_allowed_resource_actions = [
						"Not Allowed Resource Actions value",
					]
				),
			]
		),
	]
	is_built_in = True,
)

result = await graph_client.device_management.role_definitions.by_role_definition_id('roleDefinition-id').patch(request_body = request_body)


```