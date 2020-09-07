---
ms.openlocfilehash: 8dc947f584d3433f0638a72f4db86ac2680c8dbf
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497789"
---
### <a name="sqlconnection-can-no-longer-connect-to-sql-server-1997-or-databases-using-the-via-adapter"></a><span data-ttu-id="312c4-101">SqlConnection kann keine Verbindung mit SQL Server 1997 oder Datenbanken herstellen, die den VIA-Adapter verwenden</span><span class="sxs-lookup"><span data-stu-id="312c4-101">SqlConnection can no longer connect to SQL Server 1997 or databases using the VIA adapter</span></span>

#### <a name="details"></a><span data-ttu-id="312c4-102">Details</span><span class="sxs-lookup"><span data-stu-id="312c4-102">Details</span></span>

<span data-ttu-id="312c4-103">Verbindungen mit SQL Server-Datenbanken unter Verwendung des [Virtual Interface Adapter-Protokolls (VIA)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms191229(v=sql.105)) werden nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="312c4-103">Connections to SQL Server databases using the [Virtual Interface Adapter (VIA) protocol](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms191229(v=sql.105)) are no longer supported.</span></span> <span data-ttu-id="312c4-104">Das Protokoll, das verwendet wird, um eine Verbindung mit der SQL Server-Datenbank herzustellen, wird in der Verbindungszeichenfolge angezeigt.</span><span class="sxs-lookup"><span data-stu-id="312c4-104">The protocol used to connect to a SQL Server database is visible in the connection string.</span></span> <span data-ttu-id="312c4-105">Eine VIA-Verbindung bleibt über &lt;servername&gt; erhalten.</span><span class="sxs-lookup"><span data-stu-id="312c4-105">A VIA connection will contain via:&lt;servername&gt;.</span></span> <span data-ttu-id="312c4-106">Wenn diese App über ein anderes Protokoll als das VIA-Protokoll eine Verbindung mit SQL herstellt (z. B. tcp: oder np:) kommt es nicht zu einem Breaking Change.</span><span class="sxs-lookup"><span data-stu-id="312c4-106">If this app is connecting to SQL via a protocol other than VIA (tcp: or np: for example), then no breaking change will be encountered.</span></span> <span data-ttu-id="312c4-107">Außerdem werden Verbindungen mit SQL Server 7 (1997) nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="312c4-107">Also, connections to SQL Server 7 (1997) are no longer supported.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="312c4-108">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="312c4-108">Suggestion</span></span>

<span data-ttu-id="312c4-109">Das VIA-Protokoll ist veraltet. Daher sollte ein anderes Protokoll verwendet werden, um eine Verbindung mit SQL-Datenbanken herzustellen.</span><span class="sxs-lookup"><span data-stu-id="312c4-109">The VIA protocol is deprecated, so an alternative protocol should be used to connect to SQL databases.</span></span> <span data-ttu-id="312c4-110">TCP/IP ist das am häufigsten verwendete Protokoll.</span><span class="sxs-lookup"><span data-stu-id="312c4-110">The most common protocol used is TCP/IP.</span></span> <span data-ttu-id="312c4-111">Weitere Informationen zum Herstellen einer Verbindung über TCP/IP finden Sie unter [Aktivieren des TCP/IP-Protokolls für eine Datenbankinstanz](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb909712(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="312c4-111">For more information about connecting through TCP/IP, see [Enable the TCP/IP protocol for a database instance](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb909712(v=vs.90)).</span></span> <span data-ttu-id="312c4-112">Wenn Sie nur über ein Intranet auf eine Datenbank zugreifen, ist die Leistung des Protokolls für freigegebene Pipes möglicherweise besser, wenn das Netzwerk langsam ist.</span><span class="sxs-lookup"><span data-stu-id="312c4-112">If the database is only accessed from within an intranet, the shared pipes protocol may provide better performance if the network is slow.</span></span>

| <span data-ttu-id="312c4-113">name</span><span class="sxs-lookup"><span data-stu-id="312c4-113">Name</span></span>    | <span data-ttu-id="312c4-114">Wert</span><span class="sxs-lookup"><span data-stu-id="312c4-114">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="312c4-115">Bereich</span><span class="sxs-lookup"><span data-stu-id="312c4-115">Scope</span></span>   |<span data-ttu-id="312c4-116">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="312c4-116">Edge</span></span>|
|<span data-ttu-id="312c4-117">Version</span><span class="sxs-lookup"><span data-stu-id="312c4-117">Version</span></span>|<span data-ttu-id="312c4-118">4.5</span><span class="sxs-lookup"><span data-stu-id="312c4-118">4.5</span></span>|
|<span data-ttu-id="312c4-119">Typ</span><span class="sxs-lookup"><span data-stu-id="312c4-119">Type</span></span>|<span data-ttu-id="312c4-120">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="312c4-120">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="312c4-121">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="312c4-121">Affected APIs</span></span>

- <xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String)>
- <xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String,System.Data.SqlClient.SqlCredential)>

<!--

#### Affected APIs

- `M:System.Data.SqlClient.SqlConnection.#ctor(System.String)`
- `M:System.Data.SqlClient.SqlConnection.#ctor(System.String,System.Data.SqlClient.SqlCredential)`

-->
