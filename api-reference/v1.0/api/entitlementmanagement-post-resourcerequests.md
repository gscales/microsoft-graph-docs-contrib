---
title: "Create accessPackageResourceRequest"
description: "Create a new accessPackageResourceRequest."
ms.localizationpriority: medium
author: "markwahl-msft"
ms.prod: "governance"
doc_type: "apiPageType"
---

# Create accessPackageResourceRequest

Namespace: microsoft.graph

Create a new [accessPackageResourceRequest](../resources/accesspackageresourcerequest.md) object to request the addition of a resource to an access package catalog, update of a resource, or the removal of a resource from a catalog.  A resource must be included in an access package catalog before a [role of that resource](../resources/accesspackageresourcerole.md) can be added to an access package.

To add an Azure AD group as a resource to a catalog, set the **requestType** to be `adminAdd`, and a `resource` representing the resource. The value of the **originSystem** property within the `resource` should be `AadGroup` and the value of the **originId** is the identifier of the group.

To add an Azure AD application as a resource to a catalog, set the **requestType** to be `adminAdd`, and a `resource` representing the resource. The value of the **originSystem** property within the `resource` should be `AadApplication` and the value of the **originId** is the identifier of the [servicePrincipal](../resources/serviceprincipal.md).

To add a SharePoint Online site an as a resource to a catalog, set the **requestType** to be `adminAdd`, and a `resource` representing the resource. The value of the **originSystem** property within the `resource` should be `SharePointOnline` and the value of the **originId** is the URI of the site.

To remove a resource from a catalog, set the **requestType** to be `adminRemove`, and the `resource` to contain the `id` of the [resource](../resources/accesspackageresource.md) object to be removed.  The resource object can be retrieved using [list resources](accesspackagecatalog-list-resources.md).

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged) |
|:---------------------------------------|:--------------------------------------------|
| Delegated (work or school account)     | EntitlementManagement.ReadWrite.All  |
| Delegated (personal Microsoft account) | Not supported. |
| Application                            | EntitlementManagement.ReadWrite.All |

To add an Azure AD group as a resource to a catalog, using delegated permissions, the user requesting to add a group should be an owner of the group or in a directory role that allows them to modify groups. If using application permissions, the application requesting to add the group should also be assigned the `Group.ReadWrite.All` permission.

To add an Azure AD application as a resource to a catalog, using delegated permissions, the user requesting to add an application should be an owner of the application or in a directory role that allows them to modify application role assignments.

## HTTP request

<!-- { "blockType": "ignored" } -->

```http
POST /identityGovernance/entitlementManagement/resourceRequests
```

## Request headers

| Name          | Description   |
|:--------------|:--------------|
| Authorization | Bearer {token}. Required. |
| Content-Type  | application/json. Required.  |

## Request body

In the request body, supply a JSON representation of an [accessPackageResourceRequest](../resources/accesspackageresourcerequest.md) object. Include the `resource` relationship with an [accessPackageResource](../resources/accesspackageresource.md) object as part of the request, and a `catalog` object containing its `id`.

If successful, this method returns a `201 Created` response code and a new [accessPackageResourceRequest](../resources/accesspackageresourcerequest.md) object in the response body.

## Examples

### Example 1: Create an accessPackageResourceRequest for adding a group as a resource

#### Request

The following is an example of the request.

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "create_accesspackageresourcerequest_from_accesspackageresourcerequests4"
}-->

```http
POST https://graph.microsoft.com/v1.0/identityGovernance/entitlementManagement/resourceRequests
Content-type: application/json

{
  "requestType": "adminAdd",
  "resource": {
    "displayName": "Test group",
    "originId": "8ab659d0-3839-427d-8c54-5ae92f0b3e2e",
    "originSystem": "AadGroup"
  },
  "catalog": {
    "id": "beedadfe-01d5-4025-910b-84abb9369997"
  }
}
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/create-accesspackageresourcerequest-from-accesspackageresourcerequests4-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/create-accesspackageresourcerequest-from-accesspackageresourcerequests4-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/create-accesspackageresourcerequest-from-accesspackageresourcerequests4-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/create-accesspackageresourcerequest-from-accesspackageresourcerequests4-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/create-accesspackageresourcerequest-from-accesspackageresourcerequests4-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/create-accesspackageresourcerequest-from-accesspackageresourcerequests4-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/create-accesspackageresourcerequest-from-accesspackageresourcerequests4-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Python](#tab/python)
[!INCLUDE [sample-code](../includes/snippets/python/create-accesspackageresourcerequest-from-accesspackageresourcerequests4-python-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

#### Response

The following is an example of the response.

> **Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.accessPackageResourceRequest"
} -->

```http
HTTP/1.1 201 Created
Content-type: application/json

{
  "id": "acc2294e-f37f-42d3-981d-4e83847ed0ce",
  "requestType": "adminAdd",
  "state": "delivered"
}
```

### Example 2: Create an accessPackageResourceRequest for adding an application as a resource

#### Request

The following is an example of the request.

<!-- {
  "blockType": "request",
  "name": "create_accesspackageresourcerequest_from_accesspackageresourcerequests_app"
}-->

```http
POST https://graph.microsoft.com/v1.0/identityGovernance/entitlementManagement/resourceRequests
Content-type: application/json

{
  "requestType": "adminAdd",
  "resource": {
    "originId": "e81d7f57-0840-45e1-894b-f505c1bdcc1f",
    "originSystem": "AadApplication"
  },
  "catalog": {
    "id": "beedadfe-01d5-4025-910b-84abb9369997"
  }
}
```


#### Response

The following is an example of the response.

> **Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.accessPackageResourceRequest"
} -->

```http
HTTP/1.1 201 Created
Content-type: application/json

{
  "id": "acc2294e-f37f-42d3-981d-4e83847ed0ce",
  "requestType": "adminAdd",
  "state": "delivered"
}
```


### Example 3: Create an accessPackageResourceRequest for adding a SharePoint Online site as a resource

#### Request

The following is an example of the request.

<!-- {
  "blockType": "request",
  "name": "create_accesspackageresourcerequest_from_accesspackageresourcerequests_spo"
}-->

```http
POST https://graph.microsoft.com/v1.0/identityGovernance/entitlementManagement/resourceRequests
Content-type: application/json

{
  "requestType": "adminAdd",
  "resource": {
    "originId": "https://microsoft.sharepoint.com/sites/Example",
    "originSystem": "SharePointOnline"
  },
  "catalog": {
    "id": "beedadfe-01d5-4025-910b-84abb9369997"
  }
}
```


#### Response

The following is an example of the response.

> **Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.accessPackageResourceRequest"
} -->

```http
HTTP/1.1 201 Created
Content-type: application/json

{
  "id": "acc2294e-f37f-42d3-981d-4e83847ed0ce",
  "requestType": "adminAdd",
  "state": "delivered"
}
```


### Example 4: Create an accessPackageResourceRequest for removing a resource

#### Request

The following is an example of the request.

<!-- {
  "blockType": "request",
  "name": "create_accesspackageresourcerequest_from_accesspackageresourcerequests_remove"
}-->

```http
POST https://graph.microsoft.com/v1.0/identityGovernance/entitlementManagement/resourceRequests
Content-type: application/json

{
  "requestType": "adminRemove",
  "resource": {
    "id": "1d0bb962-5bb0-4b16-a488-fda7a788b9ec"
  },
  "catalog": {
    "id": "beedadfe-01d5-4025-910b-84abb9369997"
  }
}
```


#### Response

The following is an example of the response.

> **Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.accessPackageResourceRequest"
} -->

```http
HTTP/1.1 201 Created
Content-type: application/json

{
  "id": "acc2294e-f37f-42d3-981d-4e83847ed0ce",
  "requestType": "adminRemove",
  "state": "delivered"
}
```
