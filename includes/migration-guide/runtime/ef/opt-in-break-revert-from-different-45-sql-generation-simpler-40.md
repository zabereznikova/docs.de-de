---
ms.openlocfilehash: 346fb6ecd43f7f93529e45f169c79b7acacc9c1f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497818"
---
### <a name="opt-in-break-to-revert-from-different-45-sql-generation-to-simpler-40-sql-generation"></a><span data-ttu-id="5e2c5-101">Aktivierte Unterbrechung zur Wiederherstellung der SQL-Generationen 4.0 oder 4.5</span><span class="sxs-lookup"><span data-stu-id="5e2c5-101">Opt-in break to revert from different 4.5 SQL generation to simpler 4.0 SQL generation</span></span>

#### <a name="details"></a><span data-ttu-id="5e2c5-102">Details</span><span class="sxs-lookup"><span data-stu-id="5e2c5-102">Details</span></span>

<span data-ttu-id="5e2c5-103">Abfragen, die JOIN-Anweisungen erzeugen und einen Aufruf an eine Einschränkungsoperation enthalten, ohne zuvor OrderBy zu verwenden, generieren nun einfacheres SQL.</span><span class="sxs-lookup"><span data-stu-id="5e2c5-103">Queries that produce JOIN statements and contain a call to a limiting operation without first using OrderBy now produce simpler SQL.</span></span> <span data-ttu-id="5e2c5-104">Nach dem Upgrade auf .NET Framework 4.5 generieren diese Abfragen komplizierteres SQL als vorherige Versionen.</span><span class="sxs-lookup"><span data-stu-id="5e2c5-104">After upgrading to .NET Framework 4.5, these queries produced more complicated SQL than previous versions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="5e2c5-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="5e2c5-105">Suggestion</span></span>

<span data-ttu-id="5e2c5-106">Dieses Feature ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="5e2c5-106">This feature is disabled by default.</span></span> <span data-ttu-id="5e2c5-107">Wenn Entity Framework zusätzliche JOIN-Anweisungen generiert, die Leistungseinbußen verursachen, können Sie dieses Feature aktivieren, indem Sie den folgenden Eintrag zum <code>&lt;appSettings&gt;</code>-Bereich der Anwendungskonfigurationsdatei (app.config) hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="5e2c5-107">If Entity Framework generates extra JOIN statements that cause performance degradation, you can enable this feature by adding the following entry to the <code>&lt;appSettings&gt;</code> section of the application configuration (app.config) file:</span></span><pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyLimitOperations&quot; value=&quot;true&quot; /&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="5e2c5-108">name</span><span class="sxs-lookup"><span data-stu-id="5e2c5-108">Name</span></span>    | <span data-ttu-id="5e2c5-109">Wert</span><span class="sxs-lookup"><span data-stu-id="5e2c5-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5e2c5-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="5e2c5-110">Scope</span></span>   |<span data-ttu-id="5e2c5-111">Transparent</span><span class="sxs-lookup"><span data-stu-id="5e2c5-111">Transparent</span></span>|
|<span data-ttu-id="5e2c5-112">Version</span><span class="sxs-lookup"><span data-stu-id="5e2c5-112">Version</span></span>|<span data-ttu-id="5e2c5-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="5e2c5-113">4.5.2</span></span>|
|<span data-ttu-id="5e2c5-114">Typ</span><span class="sxs-lookup"><span data-stu-id="5e2c5-114">Type</span></span>|<span data-ttu-id="5e2c5-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="5e2c5-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="5e2c5-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="5e2c5-116">Affected APIs</span></span>

<span data-ttu-id="5e2c5-117">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="5e2c5-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
