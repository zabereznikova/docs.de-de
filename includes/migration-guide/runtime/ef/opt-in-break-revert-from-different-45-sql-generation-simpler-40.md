---
ms.openlocfilehash: e5d81d791e1a2f1a2dbdafc787dec1227423883d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803276"
---
### <a name="opt-in-break-to-revert-from-different-45-sql-generation-to-simpler-40-sql-generation"></a><span data-ttu-id="7d033-101">Aktivierte Unterbrechung zur Wiederherstellung der SQL-Generationen 4.0 oder 4.5</span><span class="sxs-lookup"><span data-stu-id="7d033-101">Opt-in break to revert from different 4.5 SQL generation to simpler 4.0 SQL generation</span></span>

|   |   |
|---|---|
|<span data-ttu-id="7d033-102">Details</span><span class="sxs-lookup"><span data-stu-id="7d033-102">Details</span></span>|<span data-ttu-id="7d033-103">Abfragen, die JOIN-Anweisungen erzeugen und einen Aufruf an eine Einschränkungsoperation enthalten, ohne zuvor OrderBy zu verwenden, generieren nun einfacheres SQL.</span><span class="sxs-lookup"><span data-stu-id="7d033-103">Queries that produce JOIN statements and contain a call to a limiting operation without first using OrderBy now produce simpler SQL.</span></span> <span data-ttu-id="7d033-104">Nach dem Upgrade auf .NET Framework 4.5 generieren diese Abfragen komplizierteres SQL als vorherige Versionen.</span><span class="sxs-lookup"><span data-stu-id="7d033-104">After upgrading to .NET Framework 4.5, these queries produced more complicated SQL than previous versions.</span></span>|
|<span data-ttu-id="7d033-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="7d033-105">Suggestion</span></span>|<span data-ttu-id="7d033-106">Dieses Feature ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="7d033-106">This feature is disabled by default.</span></span> <span data-ttu-id="7d033-107">Wenn Entity Framework zusätzliche JOIN-Anweisungen generiert, die Leistungseinbußen verursachen, können Sie dieses Feature aktivieren, indem Sie den folgenden Eintrag zum <code>&lt;appSettings&gt;</code>-Bereich der Anwendungskonfigurationsdatei (app.config) hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="7d033-107">If Entity Framework generates extra JOIN statements that cause performance degradation, you can enable this feature by adding the following entry to the <code>&lt;appSettings&gt;</code> section of the application configuration (app.config) file:</span></span><pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyLimitOperations&quot; value=&quot;true&quot; /&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="7d033-108">`Scope`</span><span class="sxs-lookup"><span data-stu-id="7d033-108">Scope</span></span>|<span data-ttu-id="7d033-109">Transparent</span><span class="sxs-lookup"><span data-stu-id="7d033-109">Transparent</span></span>|
|<span data-ttu-id="7d033-110">Version</span><span class="sxs-lookup"><span data-stu-id="7d033-110">Version</span></span>|<span data-ttu-id="7d033-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="7d033-111">4.5.2</span></span>|
|<span data-ttu-id="7d033-112">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="7d033-112">Type</span></span>|<span data-ttu-id="7d033-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="7d033-113">Runtime</span></span>|
