---
ms.openlocfilehash: 7f7e718d543a4abdf2b8a87e52d8c0e2ba28203f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496409"
---
### <a name="adonet-now-attempts-to-automatically-reconnect-broken-sql-connections"></a><span data-ttu-id="a7801-101">ADO.NET versucht nun, unterbrochene SQL-Verbindungen automatisch wiederherzustellen</span><span class="sxs-lookup"><span data-stu-id="a7801-101">ADO.NET now attempts to automatically reconnect broken SQL connections</span></span>

#### <a name="details"></a><span data-ttu-id="a7801-102">Details</span><span class="sxs-lookup"><span data-stu-id="a7801-102">Details</span></span>

<span data-ttu-id="a7801-103">Ab .NET Framework 4.5.1 versucht .NET Framework, unterbrochene SQL-Verbindungen automatisch wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="a7801-103">Beginning in the .NET Framework 4.5.1, the .NET Framework will attempt to automatically reconnect broken SQL connections.</span></span> <span data-ttu-id="a7801-104">Obwohl dies in der Regel dazu führt, dass Apps zuverlässiger werden, gibt es Grenzfälle, in denen eine App wissen muss, dass die Verbindung getrennt wurde, sodass sie bei der Wiederherstellung der Verbindung bestimmte Aktionen ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="a7801-104">Although this will typically make apps more reliable, there are edge cases in which an app needs to know that the connection was lost so that it can take some action upon reconnection.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a7801-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="a7801-105">Suggestion</span></span>

<span data-ttu-id="a7801-106">Wenn dieses Feature aus Kompatibilitätsgründen nicht erwünscht ist, kann es durch Festlegen der <xref:System.Data.SqlClient.SqlConnectionStringBuilder.ConnectRetryCount?displayProperty=fullName>-Eigenschaft einer Verbindungszeichenfolge (oder <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=fullName>) auf 0 (null) deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="a7801-106">If this feature is undesirable due to compatibility concerns, it can be disabled by setting the <xref:System.Data.SqlClient.SqlConnectionStringBuilder.ConnectRetryCount?displayProperty=fullName> property of a connection string (or <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=fullName>) to 0.</span></span>

| <span data-ttu-id="a7801-107">name</span><span class="sxs-lookup"><span data-stu-id="a7801-107">Name</span></span>    | <span data-ttu-id="a7801-108">Wert</span><span class="sxs-lookup"><span data-stu-id="a7801-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a7801-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="a7801-109">Scope</span></span>   |<span data-ttu-id="a7801-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a7801-110">Edge</span></span>|
|<span data-ttu-id="a7801-111">Version</span><span class="sxs-lookup"><span data-stu-id="a7801-111">Version</span></span>|<span data-ttu-id="a7801-112">4.5.1</span><span class="sxs-lookup"><span data-stu-id="a7801-112">4.5.1</span></span>|
|<span data-ttu-id="a7801-113">Typ</span><span class="sxs-lookup"><span data-stu-id="a7801-113">Type</span></span>|<span data-ttu-id="a7801-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="a7801-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="a7801-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="a7801-115">Affected APIs</span></span>

- <xref:System.Data.IDbConnection.ConnectionString?displayProperty=nameWithType>
- <xref:System.Data.SqlClient.SqlConnection.ConnectionString?displayProperty=nameWithType>
- <xref:System.Configuration.ConnectionStringSettings.ConnectionString?displayProperty=nameWithType>
- <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType>
- <xref:System.Data.Common.DbConnectionStringBuilder.ConnectionString?displayProperty=nameWithType>
- <xref:System.Data.SqlClient.SqlConnectionStringBuilder.%23ctor>
- <xref:System.Data.SqlClient.SqlConnectionStringBuilder.%23ctor(System.String)>
- <xref:System.Data.Common.DbConnectionStringBuilder.%23ctor>
- <xref:System.Data.Common.DbConnectionStringBuilder.%23ctor(System.Boolean)>

<!--

#### Affected APIs

- `P:System.Data.IDbConnection.ConnectionString`
- `P:System.Data.SqlClient.SqlConnection.ConnectionString`
- `P:System.Configuration.ConnectionStringSettings.ConnectionString`
- `P:System.Data.Common.DbConnection.ConnectionString`
- `P:System.Data.Common.DbConnectionStringBuilder.ConnectionString`
- `M:System.Data.SqlClient.SqlConnectionStringBuilder.#ctor`
- `M:System.Data.SqlClient.SqlConnectionStringBuilder.#ctor(System.String)`
- `M:System.Data.Common.DbConnectionStringBuilder.#ctor`
- `M:System.Data.Common.DbConnectionStringBuilder.#ctor(System.Boolean)`

-->
