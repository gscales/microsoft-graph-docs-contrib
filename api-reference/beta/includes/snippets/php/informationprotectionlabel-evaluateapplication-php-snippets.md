---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new EvaluateApplicationPostRequestBody();
$contentInfo = new ContentInfo();
$contentInfo->setOdataType('#microsoft.graph.contentInfo');
$contentInfo->setFormat(new ContentFormat('default'));
$ContentInfo->setIdentifier(null);
$contentInfo->setState(new ContentState('rest'));
$metadataKeyValuePair1 = new KeyValuePair();
$metadataKeyValuePair1->setOdataType('#microsoft.graph.keyValuePair');
$metadataKeyValuePair1->setName('MSIP_Label_722a5300-ac39-4c9a-88e3-f54c46676417_Enabled');
$metadataKeyValuePair1->setValue('True');
$metadataArray []= $metadataKeyValuePair1;
$metadataKeyValuePair2 = new KeyValuePair();
$metadataKeyValuePair2->setOdataType('#microsoft.graph.keyValuePair');
$metadataKeyValuePair2->setName('MSIP_Label_722a5300-ac39-4c9a-88e3-f54c46676417_Method');
$metadataKeyValuePair2->setValue('Standard');
$metadataArray []= $metadataKeyValuePair2;
$metadataKeyValuePair3 = new KeyValuePair();
$metadataKeyValuePair3->setOdataType('#microsoft.graph.keyValuePair');
$metadataKeyValuePair3->setName('MSIP_Label_722a5300-ac39-4c9a-88e3-f54c46676417_SetDate');
$metadataKeyValuePair3->setValue('1/1/0001 12:00:00 AM');
$metadataArray []= $metadataKeyValuePair3;
$metadataKeyValuePair4 = new KeyValuePair();
$metadataKeyValuePair4->setOdataType('#microsoft.graph.keyValuePair');
$metadataKeyValuePair4->setName('MSIP_Label_722a5300-ac39-4c9a-88e3-f54c46676417_SiteId');
$metadataKeyValuePair4->setValue('cfa4cf1d-a337-4481-aa99-19d8f3d63f7c');
$metadataArray []= $metadataKeyValuePair4;
$metadataKeyValuePair5 = new KeyValuePair();
$metadataKeyValuePair5->setOdataType('#microsoft.graph.keyValuePair');
$metadataKeyValuePair5->setName('MSIP_Label_722a5300-ac39-4c9a-88e3-f54c46676417_Name');
$metadataKeyValuePair5->setValue('General');
$metadataArray []= $metadataKeyValuePair5;
$metadataKeyValuePair6 = new KeyValuePair();
$metadataKeyValuePair6->setOdataType('#microsoft.graph.keyValuePair');
$metadataKeyValuePair6->setName('MSIP_Label_722a5300-ac39-4c9a-88e3-f54c46676417_ContentBits');
$metadataKeyValuePair6->setValue('0');
$metadataArray []= $metadataKeyValuePair6;
$metadataKeyValuePair7 = new KeyValuePair();
$metadataKeyValuePair7->setOdataType('#microsoft.graph.keyValuePair');
$metadataKeyValuePair7->setName('MSIP_Label_722a5300-ac39-4c9a-88e3-f54c46676417_ActionId');
$metadataKeyValuePair7->setValue('00000000-0000-0000-0000-000000000000');
$metadataArray []= $metadataKeyValuePair7;
$contentInfo->setMetadata($metadataArray);

$additionalData = [
'format@odata.type' => '#microsoft.graph.contentFormat',
'state@odata.type' => '#microsoft.graph.contentState',
'metadata@odata.type' => '#Collection(microsoft.graph.keyValuePair)',
];
$contentInfo->setAdditionalData($additionalData);
$requestBody->setContentInfo($contentInfo);
$labelingOptions = new LabelingOptions();
$labelingOptions->setOdataType('#microsoft.graph.labelingOptions');
$labelingOptions->setAssignmentMethod(new AssignmentMethod('standard'));
$labelingOptions->setLabelId('97309856-9c28-4ac6-9382-5f8bc20c457b');
$LabelingOptions->setDowngradeJustification(null);
$labelingOptions->setExtendedProperties([]);
$additionalData = [
'assignmentMethod@odata.type' => '#microsoft.graph.assignmentMethod',
'labelId@odata.type' => '#Guid',
'extendedProperties@odata.type' => '#Collection(microsoft.graph.keyValuePair)',
];
$labelingOptions->setAdditionalData($additionalData);
$requestBody->setLabelingOptions($labelingOptions);
$requestConfiguration = new EvaluateApplicationRequestBuilderPostRequestConfiguration();
$headers = [
	'User-Agent' => 'ContosoLOBApp/1.0',
];
$requestConfiguration->headers = $headers;


$result = $graphServiceClient->informationProtection()->policy()->labels()->evaluateApplication()->post($requestBody, $requestConfiguration)->wait();

```