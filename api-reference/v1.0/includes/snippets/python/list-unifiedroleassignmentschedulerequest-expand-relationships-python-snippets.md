---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(request_adapter)

query_params = RoleAssignmentScheduleRequestsRequestBuilder.RoleAssignmentScheduleRequestsRequestBuilderGetQueryParameters(
		select = ["principalId","action","roleDefinitionId"],
		expand = ["roleDefinition","activatedUsing","principal","targetSchedule"],
)

request_configuration = RoleAssignmentScheduleRequestsRequestBuilder.RoleAssignmentScheduleRequestsRequestBuilderGetRequestConfiguration(
query_parameters = query_params,
)

result = await graph_client.role_management.directory.role_assignment_schedule_requests.get(request_configuration = request_configuration)


```