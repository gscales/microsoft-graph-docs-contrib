---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);

$requestConfiguration = new EventRequestBuilderGetRequestConfiguration();
$queryParameters = EventRequestBuilderGetRequestConfiguration::createQueryParameters();
$queryParameters->select = ["isOnlineMeeting","onlineMeetingProvider","onlineMeeting"];
$requestConfiguration->queryParameters = $queryParameters;


$result = $graphServiceClient->me()->events()->byEventId('event-id')->get($requestConfiguration)->wait();

```