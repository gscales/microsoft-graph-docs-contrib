---
description: "Automatically generated file. DO NOT MODIFY"
---

```php

<?php

// THIS SNIPPET IS A PREVIEW VERSION OF THE SDK. NON-PRODUCTION USE ONLY
$graphServiceClient = new GraphServiceClient($tokenRequestContext, $scopes);


$graphServiceClient->chats()->byChatId('chat-id')->messages()->byChatMessageId('chatMessage-id')->hostedContents()->byChatMessageHostedContentId('chatMessageHostedContent-id')->value()->get()->wait();

```