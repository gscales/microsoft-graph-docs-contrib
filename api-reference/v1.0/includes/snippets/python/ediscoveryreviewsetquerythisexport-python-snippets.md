---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(request_adapter)

request_body = ExportPostRequestBody(
	output_name = "Export reviewset query via API",
	description = "Export for the Contoso investigation 2",
	export_options = ExportOptions.OriginalFiles | ExportOptions.Tags,
	export_structure = ExportFileStructure.Directory,
)

await graph_client.security.cases.ediscovery_cases.by_ediscovery_case_id('ediscoveryCase-id').review_sets.by_review_set_id('ediscoveryReviewSet-id').queries.by_querie_id('ediscoveryReviewSetQuery-id').microsoft_graph_security_export.post(request_body = request_body)


```