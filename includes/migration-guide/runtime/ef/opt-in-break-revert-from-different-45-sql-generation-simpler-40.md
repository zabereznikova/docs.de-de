---
ms.openlocfilehash: 22b5abbe769733e8d5ca3e78dd9e6e13b2363737
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620312"
---
### <a name="opt-in-break-to-revert-from-different-45-sql-generation-to-simpler-40-sql-generation"></a><span data-ttu-id="22eaa-101">Aktivierte Unterbrechung zur Wiederherstellung der SQL-Generationen 4.0 oder 4.5</span><span class="sxs-lookup"><span data-stu-id="22eaa-101">Opt-in break to revert from different 4.5 SQL generation to simpler 4.0 SQL generation</span></span>

#### <a name="details"></a><span data-ttu-id="22eaa-102">Details</span><span class="sxs-lookup"><span data-stu-id="22eaa-102">Details</span></span>

<span data-ttu-id="22eaa-103">Abfragen, die JOIN-Anweisungen erzeugen und einen Aufruf an eine Einschränkungsoperation enthalten, ohne zuvor OrderBy zu verwenden, generieren nun einfacheres SQL.</span><span class="sxs-lookup"><span data-stu-id="22eaa-103">Queries that produce JOIN statements and contain a call to a limiting operation without first using OrderBy now produce simpler SQL.</span></span> <span data-ttu-id="22eaa-104">Nach dem Upgrade auf .NET Framework 4.5 generieren diese Abfragen komplizierteres SQL als vorherige Versionen.</span><span class="sxs-lookup"><span data-stu-id="22eaa-104">After upgrading to .NET Framework 4.5, these queries produced more complicated SQL than previous versions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="22eaa-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="22eaa-105">Suggestion</span></span>

<span data-ttu-id="22eaa-106">Dieses Feature ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="22eaa-106">This feature is disabled by default.</span></span> <span data-ttu-id="22eaa-107">Wenn Entity Framework zusätzliche JOIN-Anweisungen generiert, die Leistungseinbußen verursachen, können Sie dieses Feature aktivieren, indem Sie den folgenden Eintrag zum <code>&lt;appSettings&gt;</code>-Bereich der Anwendungskonfigurationsdatei (app.config) hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="22eaa-107">If Entity Framework generates extra JOIN statements that cause performance degradation, you can enable this feature by adding the following entry to the <code>&lt;appSettings&gt;</code> section of the application configuration (app.config) file:</span></span><pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyLimitOperations&quot; value=&quot;true&quot; /&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="22eaa-108">name</span><span class="sxs-lookup"><span data-stu-id="22eaa-108">Name</span></span>    | <span data-ttu-id="22eaa-109">Wert</span><span class="sxs-lookup"><span data-stu-id="22eaa-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="22eaa-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="22eaa-110">Scope</span></span>   |<span data-ttu-id="22eaa-111">Transparent</span><span class="sxs-lookup"><span data-stu-id="22eaa-111">Transparent</span></span>|
|<span data-ttu-id="22eaa-112">Version</span><span class="sxs-lookup"><span data-stu-id="22eaa-112">Version</span></span>|<span data-ttu-id="22eaa-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="22eaa-113">4.5.2</span></span>|
|<span data-ttu-id="22eaa-114">Typ</span><span class="sxs-lookup"><span data-stu-id="22eaa-114">Type</span></span>|<span data-ttu-id="22eaa-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="22eaa-115">Runtime</span></span>|
