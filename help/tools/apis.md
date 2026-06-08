---
title: 適用於建置器的API
description: 使用Adobe CX Enterprise API建立自訂應用程式和整合。
index: false
source-git-commit: 63f5958eaa227ea21fa5b193a2ac76a69fd349cb
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 3%

---


# 適用於建置器的API

<!-- last-modified: 2026-06-02 -->

![Adobe CX Enterprise API](../assets/hero-apis.png)

Adobe CX Enterprise API可讓開發人員和AI輔助編碼代理工具直接存取Adobe資料和工作流程。 使用這些功能來建立自訂應用程式、自動化整合，並將Adobe功能內嵌到您自己的系統中。 當您需要以程式設計方式完整控制系統整合，或需要以Adobe資料為基礎建立應用程式時，API是您正確的選擇。 如需代理程式導向的對話式存取Adobe工作流程，請參閱[MCP伺服器](mcp-servers.md)。

## Adobe CX Enterprise API

Adobe CX Enterprise API公開可支援Adobe Experience Platform、Journey Optimizer和Customer Journey Analytics等產品的核心資料與作業。 每個API都遵循API優先設計，讓開發人員和AI輔助編碼代理工具可直接、程式化地存取Adobe內部使用的相同功能。 使用這些功能來建立自訂應用程式、自動化工作流程，並將Adobe資料整合到您自己的系統中。

<!--
CARDS

* https://developer.adobe.com/audience-manager/
  {title = Audience Manager}
  {description = Audience management and activation workflows.}
  {cta = Explore API}
  {target = _blank}
  {image = ../assets/apis-aam-card.png}

* https://developer.adobe.com/client-sdks/home/
  {title = Client SDKs}
  {description = Mobile SDKs, edge SDKs, and in-app messaging.}
  {cta = Explore API}
  {target = _blank}
  {image = ../assets/apis-cxenterprise-card.png}

* https://developer.adobe.com/cja-apis/docs/
  {title = Customer Journey Analytics}
  {description = Analytics data access, reporting, and CJA insights workflows.}
  {cta = Explore API}
  {target = _blank}
  {image = ../assets/apis-cja-card.png}

* https://developer.adobe.com/data-collection-apis/docs/
  {title = Data Collection}
  {description = Edge Network data ingestion, real-time event collection, and streaming data delivery.}
  {cta = Explore API}
  {target = _blank}
  {image = ../assets/apis-aep-card.png}

* https://developer.adobe.com/developer-console/docs/guides/
  {title = Developer Console}
  {description = API project setup, authentication, and credential management.}
  {cta = Explore API}
  {target = _blank}
  {image = ../assets/apis-cxenterprise-card.png}

* https://developer.adobe.com/events/docs/
  {title = Events}
  {description = Event-driven integrations, webhooks, and automation triggers.}
  {cta = Explore API}
  {target = _blank}
  {image = ../assets/apis-cxenterprise-card.png}

* https://experienceleague.adobe.com/zh-hant/docs/experience-platform/privacy/home
  {title = Privacy}
  {description = Privacy workflows, data governance, and data subject requests.}
  {cta = Explore API}
  {target = _blank}
  {image = ../assets/apis-aep-card.png}

* https://developer.adobe.com/experience-platform-apis/
  {title = Adobe Experience Platform}
  {description = CRUD operations for datasets, schemas, profiles, identities, queries, and segmentation.}
  {cta = Explore API}
  {target = _blank}
  {image = ../assets/apis-aep-card.png}

* https://developer.adobe.com/journey-optimizer-apis/
  {title = Adobe Journey Optimizer}
  {description = Journey orchestration, campaign management, content templates, and offer decisioning.}
  {cta = Explore API}
  {target = _blank}
  {image = ../assets/apis-ajo-card.png}

* https://developer.adobe.com/analytics-apis/docs/2.0/
  {title = Adobe Analytics}
  {description = Reporting, data feeds, calculated metrics, and segment management.}
  {cta = Explore API}
  {target = _blank}
  {image = ../assets/apis-analytics-card.png}

* https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developing/apis-and-extensions
  {title = AEM as a Cloud Service}
  {description = Content, asset, and workflow management APIs for Adobe Experience Manager.}
  {cta = Explore API}
  {target = _blank}
  {image = ../assets/apis-aem-card.png}

* https://developer.adobe.com/commerce/webapi/
  {title = Adobe Commerce}
  {description = REST and GraphQL APIs for catalog, cart, orders, customers, and promotions.}
  {cta = Explore API}
  {target = _blank}
  {image = ../assets/apis-commerce-card.png}

* https://developer.adobe.com/umapi/
  {title = User Management}
  {description = User management, identity administration, and enterprise account automation.}
  {cta = Explore API}
  {target = _blank}
  {image = ../assets/apis-cxenterprise-card.png}
-->

## 適用於建置器與MCP伺服器的API

當您需要完全控制系統整合或正在建置自訂應用程式時，請使用API。 當您希望AI代理程式直接搭配Adobe工作流程使用時，請使用MCP伺服器。

| | API | MCP伺服器 |
| --- | --- | --- |
| 直接系統整合 | 是 | 有時 |
| 代理程式友善協調 | 有限 | 是 |
| 原始資料存取 | 是 | 通常是抽象的 |
| 自訂應用程式開發 | 主要使用案例 | 次要 |
| AI輔助工作流程 | 支援 | 主要使用案例 |

## 開始使用建置器適用的API

![連線到Adobe CX Enterprise API的IDE](../assets/hero-connect-apis.gif)

Adobe CX Enterprise API在建置之前需要兩個條件：來自Adobe Developer Console的已驗證憑證，以及新增至您專案的API檔案，讓您的程式碼代理程式可以可靠地與Adobe API搭配使用。

### 在Adobe Developer Console中設定API認證

所有Adobe CX Enterprise API存取是透過[Adobe Developer Console](https://developer.adobe.com/developer-console/docs/guides/)管理。 建立專案、新增應用程式需求的API並產生認證。

1. 登入並在Adobe Developer Console中[建立專案](https://developer.adobe.com/developer-console/docs/guides/projects/)。
2. [新增您所需的Adobe CX Enterprise應用程式的API](https://developer.adobe.com/developer-console/docs/guides/services/)。
3. 選擇[驗證型別](https://developer.adobe.com/developer-console/docs/guides/authentication/)。 將&#x200B;**OAuth伺服器對伺服器**&#x200B;用於自動化工作流程，或將&#x200B;**OAuth Web應用程式**&#x200B;用於面向使用者的應用程式。
4. 產生您的認證。 請注意使用者端ID、使用者端密碼和權杖端點是否用於您的應用程式。

大部分的Adobe CX Enterprise API都需要應用程式授權。 如果您的Developer Console專案無法使用API，請聯絡您的Adobe代表。

### 將Adobe API內容新增至專案

當您將正確的參考資料新增到專案時，AI編碼代理程式可以可靠地探索和使用Adobe API。 適用於任何已發佈OpenAPI規格的Adobe CX Enterprise API。

**1. 尋找API規格**

瀏覽上方列出的[Adobe CX Enterprise API](#adobe-cx-enterprise-apis)，或直接前往[Adobe Developer API目錄](https://developer.adobe.com/apis)。

**2. 下載OpenAPI規格**

在您的專案中建立`/specs`目錄。 從[developer.adobe.com](https://developer.adobe.com/apis)上的API參考頁面下載OpenAPI YAML並儲存在該處。 新增`README.md`以記錄來源URL和下載日期。

```
/specs/README.md
/specs/aem-assets.openapi.yaml
```

>[!TIP]
>簽入的快照可為您的編碼代理程式提供穩定、可重複的行為，並使API變更顯示在您的Git記錄中。

**3. 產生API索引**

將此提示貼到您的程式碼代理程式中，將`<API-SPEC-FILE>`取代為您的檔案名稱：

```
Read /specs/<API-SPEC-FILE>.openapi.yaml and generate /docs/<API-SPEC-FILE>.api.md.

Create a concise API index for AI coding agents. For each operation include: operationId, HTTP method, path, purpose, authentication requirements, required inputs, response shape, common error responses, pagination behavior, asynchronous behavior, and deprecation status.

Do not invent endpoints, parameters, request bodies, response fields, or behavior not present in the OpenAPI specification.
```

**4. 產生代理程式指示**

```
Read /specs/<API-SPEC-FILE>.openapi.yaml and /docs/<API-SPEC-FILE>.api.md.

Generate AGENTS.md. Instructions should:
- Treat the OpenAPI specification as the source of truth.
- Use the API index as a navigation guide.
- Never invent endpoints, parameters, response fields, or status codes.
- Prefer documented operationIds.
- Avoid deprecated or experimental APIs unless explicitly requested.
- Follow authentication requirements defined in the specification.
- Use the local OpenAPI snapshot for implementation decisions.
```

**5. 驗證**

請要求您的程式碼代理程式僅使用產生的檔案完成簡單的工作：

```
Write a function that takes an AEM asset ID and returns the asset title and description. Use only /specs/aem-assets.openapi.yaml and /docs/aem-assets.api.md.
```

如果代理程式正確完成它而沒有發明行為，則設定完成。

**建議的專案結構**

```
project/
├── specs/
│   ├── README.md
│   └── aem-assets.openapi.yaml
├── docs/
│   └── aem-assets.api.md
└── AGENTS.md
```

**保持規格為最新**

當Adobe發佈新的API版本時：將新的快照集下載到`/specs`、更新`README.md`中的日期，並重新產生索引和`AGENTS.md`。
