---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(request_adapter)

request_body = DeviceComplianceDeviceStatus(
	odata_type = "#microsoft.graph.deviceComplianceDeviceStatus",
	device_display_name = "Device Display Name value",
	user_name = "User Name value",
	device_model = "Device Model value",
	compliance_grace_period_expiration_date_time = "2016-12-31T23:56:44.951111-08:00",
	status = ComplianceStatus.NotApplicable,
	last_reported_date_time = "2017-01-01T00:00:17.7769392-08:00",
	user_principal_name = "User Principal Name value",
)

result = await graph_client.device_management.device_compliance_policies.by_device_compliance_policie_id('deviceCompliancePolicy-id').device_statuses.by_device_statuse_id('deviceComplianceDeviceStatus-id').patch(request_body = request_body)


```