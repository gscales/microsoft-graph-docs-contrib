---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(request_adapter)

request_body = AccessPackageAssignmentPolicy(
	id = "b2eba9a1-b357-42ee-83a8-336522ed6cbf",
	access_package_id = "4c02f928-7752-49aa-8fc8-e286d973a965",
	display_name = "All Users",
	description = "All users can request for access to the directory.",
	can_extend = False,
	duration_in_days = 365,
	expiration_date_time = None,
	requestor_settings = RequestorSettings(
		scope_type = "AllExistingConnectedOrganizationSubjects",
		accept_requests = True,
		allowed_requestors = [
		]
	),
	request_approval_settings = ApprovalSettings(
		is_approval_required = True,
		is_approval_required_for_extension = False,
		is_requestor_justification_required = True,
		approval_mode = "SingleStage",
		approval_stages = [
			ApprovalStage(
				approval_stage_time_out_in_days = 14,
				is_approver_justification_required = True,
				is_escalation_enabled = False,
				escalation_time_in_minutes = 11520,
				primary_approvers = [
					GroupMembers(
						odata_type = "#microsoft.graph.groupMembers",
						is_backup = True,
						id = "d2dcb9a1-a445-42ee-83a8-476522ed6cbf",
						description = "group for users from connected organizations which have no external sponsor",
					),
					ExternalSponsors(
						odata_type = "#microsoft.graph.externalSponsors",
						is_backup = False,
					),
				]
			),
		]
	),
	questions = [
		AccessPackageMultipleChoiceQuestion(
			is_required = False,
			text = AccessPackageLocalizedContent(
				default_text = "what state are you from?",
				localized_texts = [
					AccessPackageLocalizedText(
						text = "¿De qué estado eres?",
						language_code = "es",
					),
				]
			),
			odata_type = "#microsoft.graph.accessPackageMultipleChoiceQuestion",
			choices = [
				AccessPackageAnswerChoice(
					actual_value = "AZ",
					display_value = AccessPackageLocalizedContent(
						localized_texts = [
							AccessPackageLocalizedText(
								text = "Arizona",
								language_code = "es",
							),
						]
					),
				),
				AccessPackageAnswerChoice(
					actual_value = "CA",
					display_value = AccessPackageLocalizedContent(
						localized_texts = [
							AccessPackageLocalizedText(
								text = "California",
								language_code = "es",
							),
						]
					),
				),
			]
			allows_multiple_selection = False,
		),
		AccessPackageTextInputQuestion(
			is_required = False,
			text = AccessPackageLocalizedContent(
				default_text = "Who is your manager?",
				localized_texts = [
					AccessPackageLocalizedText(
						text = "por qué necesita acceso a este paquete",
						language_code = "es",
					),
				]
			),
			odata_type = "#microsoft.graph.accessPackageTextInputQuestion",
			is_single_line_question = False,
		),
	]
)

result = await graph_client.identity_governance.entitlement_management.acce_package_assignment_policies.by_acces_package_assignment_policie_id('accessPackageAssignmentPolicy-id').put(request_body = request_body)


```