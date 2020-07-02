---
ms.openlocfilehash: 768a948849064cedb38110f5ed271717442325c0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620313"
---
### <a name="log-file-name-created-by-the-objectcontextcreatedatabase-method-has-changed-to-match-sql-server-specifications"></a><span data-ttu-id="7e361-101">Der von der ObjectContext.CreateDatabase-Methode erstellte Protokolldateiname wurde geändert, um den SQL Server-Spezifikationen zu entsprechen</span><span class="sxs-lookup"><span data-stu-id="7e361-101">Log file name created by the ObjectContext.CreateDatabase method has changed to match SQL Server specifications</span></span>

#### <a name="details"></a><span data-ttu-id="7e361-102">Details</span><span class="sxs-lookup"><span data-stu-id="7e361-102">Details</span></span>

<span data-ttu-id="7e361-103">Wenn die <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName>-Methode entweder direkt oder durch Code First mit dem SqlClient-Anbieter und einem AttachDBFilename-Wert in der Verbindungszeichenfolge aufgerufen wird, erstellt sie eine Protokolldatei namens „Dateiname_log.ldf“ anstelle von „Dateiname.ldf“ (wobei „Dateiname“ der vom AttachDBFilename-Wert angegebene Name der Datei ist).</span><span class="sxs-lookup"><span data-stu-id="7e361-103">When the <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName> method is called either directly or by using Code First with the SqlClient provider and an AttachDBFilename value in the connection string, it creates a log file named filename_log.ldf instead of filename.ldf (where filename is the name of the file specified by the AttachDBFilename value).</span></span> <span data-ttu-id="7e361-104">Diese Änderung verbessert das Debuggen, indem eine Protokolldatei bereitgestellt wird, die nach den SQL Server-Spezifikationen benannt wird.</span><span class="sxs-lookup"><span data-stu-id="7e361-104">This change improves debugging by providing a log file named according to SQL Server specifications.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7e361-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="7e361-105">Suggestion</span></span>

<span data-ttu-id="7e361-106">Wenn der Name der Protokolldatei für eine App wichtig ist, sollte die App aktualisiert werden, um das standardmäßige Dateinamenformat „_log.ldf“ zu erwarten.</span><span class="sxs-lookup"><span data-stu-id="7e361-106">If the log file name is important for an app, the app should be updated to expect the standard _log.ldf file name format.</span></span>

| <span data-ttu-id="7e361-107">name</span><span class="sxs-lookup"><span data-stu-id="7e361-107">Name</span></span>    | <span data-ttu-id="7e361-108">Wert</span><span class="sxs-lookup"><span data-stu-id="7e361-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7e361-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="7e361-109">Scope</span></span>   |<span data-ttu-id="7e361-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7e361-110">Edge</span></span>|
|<span data-ttu-id="7e361-111">Version</span><span class="sxs-lookup"><span data-stu-id="7e361-111">Version</span></span>|<span data-ttu-id="7e361-112">4.5</span><span class="sxs-lookup"><span data-stu-id="7e361-112">4.5</span></span>|
|<span data-ttu-id="7e361-113">Typ</span><span class="sxs-lookup"><span data-stu-id="7e361-113">Type</span></span>|<span data-ttu-id="7e361-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="7e361-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7e361-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="7e361-115">Affected APIs</span></span>

-<xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType></li></ul>|
