---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestBody = new AndroidStoreApp();
$requestBody->setOdataType('#microsoft.graph.androidStoreApp');
$requestBody->setDisplayName('Display Name value');
$requestBody->setDescription('Description value');
$requestBody->setPublisher('Publisher value');
$largeIcon = new MimeContent();
$largeIcon->setOdataType('microsoft.graph.mimeContent');
$largeIcon->setType('Type value');
$LargeIcon->setValue(base64_decode('dmFsdWU='));
$requestBody->setLargeIcon($largeIcon);
$requestBody->setIsFeatured(true);
$requestBody->setPrivacyInformationUrl('https://example.com/privacyInformationUrl/');
$requestBody->setInformationUrl('https://example.com/informationUrl/');
$requestBody->setOwner('Owner value');
$requestBody->setDeveloper('Developer value');
$requestBody->setNotes('Notes value');
$requestBody->setPublishingState(new MobileAppPublishingState('processing'));
$requestBody->setPackageId('Package Id value');
$requestBody->setAppStoreUrl('https://example.com/appStoreUrl/');
$minimumSupportedOperatingSystem = new AndroidMinimumOperatingSystem();
$minimumSupportedOperatingSystem->setOdataType('microsoft.graph.androidMinimumOperatingSystem');
$minimumSupportedOperatingSystem->setV4_0(true);
$minimumSupportedOperatingSystem->setV4_0_3(true);
$minimumSupportedOperatingSystem->setV4_1(true);
$minimumSupportedOperatingSystem->setV4_2(true);
$minimumSupportedOperatingSystem->setV4_3(true);
$minimumSupportedOperatingSystem->setV4_4(true);
$minimumSupportedOperatingSystem->setV5_0(true);
$minimumSupportedOperatingSystem->setV5_1(true);
$minimumSupportedOperatingSystem->setV6_0(true);
$minimumSupportedOperatingSystem->setV7_0(true);
$minimumSupportedOperatingSystem->setV7_1(true);
$minimumSupportedOperatingSystem->setV8_0(true);
$minimumSupportedOperatingSystem->setV8_1(true);
$minimumSupportedOperatingSystem->setV9_0(true);
$minimumSupportedOperatingSystem->setV10_0(true);
$minimumSupportedOperatingSystem->setV11_0(true);
$requestBody->setMinimumSupportedOperatingSystem($minimumSupportedOperatingSystem);

$result = $graphServiceClient->deviceAppManagement()->mobileApps()->post($requestBody)->wait();

```