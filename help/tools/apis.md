---
title: 適用於建置器的API
description: 使用Adobe CX Enterprise API建立自訂應用程式和整合。
last-substantial-update: 2026-06-02T00:00:00Z
index: false
source-git-commit: 9a3b90f5f1238e780a0f40b082623cd8da0e71a5
workflow-type: tm+mt
source-wordcount: '793'
ht-degree: 11%

---


# 適用於建置器的API

<!-- last-modified: 2026-06-02 -->

![Adobe CX Enterprise API](../assets/hero-apis.png)

Adobe CX Enterprise API可讓開發人員和AI輔助編碼代理工具直接存取Adobe資料和工作流程。 使用這些功能來建立自訂應用程式、自動化整合，並將Adobe功能內嵌到您自己的系統中。 當您需要以程式設計方式完整控制系統整合，或需要以Adobe資料為基礎建立應用程式時，API是您正確的選擇。 如需代理程式導向的對話式存取Adobe工作流程，請參閱[MCP伺服器](mcp-servers.md)。

## Adobe CX Enterprise API

>[!BEGINTABS]

>[!TAB Adobe Analytics]

報表、資料摘要、計算量度和區段管理。

[探索API](https://developer.adobe.com/analytics-apis/docs/2.0/)

>[!TAB Adobe Commerce]

目錄、購物車、訂單、客戶和促銷活動的REST和GraphQL API。

[探索API](https://developer.adobe.com/commerce/webapi/)

>[!TAB Adobe Experience Platform]

針對資料集、結構描述、設定檔、身分、查詢和分段的CRUD操作。

[探索API](https://developer.adobe.com/experience-platform-apis/)

>[!TAB Adobe Journey Optimizer]

歷程協調、行銷活動管理、內容範本和Offer Decisioning。

[探索API](https://developer.adobe.com/journey-optimizer-apis/)

>[!TAB AEM as a Cloud Service]

Adobe Experience Manager的內容、資產和工作流程管理API。

[探索API](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/developing/apis-and-extensions)

>[!TAB Audience Manager]

對象管理和啟用工作流程。

[探索API](https://developer.adobe.com/audience-manager/)

>[!TAB 使用者端SDK]

行動SDK、邊緣SDK和應用程式內傳訊。

[探索API](https://developer.adobe.com/client-sdks/home/)

>[!TAB Customer Journey Analytics]

Analytics資料存取、報告和CJA見解工作流程。

[探索API](https://developer.adobe.com/cja-apis/docs/)

>[!TAB 資料收集]

Edge Network資料擷取、即時事件收集和串流資料傳送。

[探索API](https://developer.adobe.com/data-collection-apis/docs/)

>[!TAB Developer Console]

API專案設定、驗證和認證管理。

[探索API](https://developer.adobe.com/developer-console/docs/guides/)

>[!TAB 活動]

事件導向的整合、Webhook和自動化觸發器。

[探索API](https://developer.adobe.com/events/docs/)

>[!TAB 隱私]

隱私權工作流程、資料控管和資料主體請求。

[探索API](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/privacy/home)

>[!TAB 用戶管理]

使用者管理、身分管理和企業帳戶自動化。

[探索API](https://developer.adobe.com/umapi/)

>[!ENDTABS]

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

## 適用於建置器與MCP伺服器的API

當您需要完全控制系統整合或正在建置自訂應用程式時，請使用API。 當您希望AI代理程式直接搭配Adobe工作流程使用時，請使用MCP伺服器。

| | API | MCP伺服器 |
| --- | --- | --- |
| 直接系統整合 | 是 | 有時 |
| 代理程式友善協調 | 有限 | 是 |
| 原始資料存取 | 是 | 通常是抽象的 |
| 自訂應用程式開發 | 主要使用案例 | 次要 |
| AI輔助工作流程 | 支援 | 主要使用案例 |
