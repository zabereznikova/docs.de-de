---
ms.openlocfilehash: c679cb2603d39f580203d9373d76481e904e6c1d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497896"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a><span data-ttu-id="1b562-101">Bei der Profilerstellung für ASP.NET MVC4-Apps kann ein schwerwiegender Fehler der Ausführungs-Engine entstehen</span><span class="sxs-lookup"><span data-stu-id="1b562-101">Profiling ASP.Net MVC4 apps can lead to Fatal Execution Engine Error</span></span>

#### <a name="details"></a><span data-ttu-id="1b562-102">Details</span><span class="sxs-lookup"><span data-stu-id="1b562-102">Details</span></span>

<span data-ttu-id="1b562-103">Profiler, die NGEN- bzw. Profilassemblys verwenden, lösen möglicherweise beim Start von ASP.NET MVC4-Anwendungen mit Profilen einen „schwerwiegenden Fehler der Ausführungs-Engine“ aus</span><span class="sxs-lookup"><span data-stu-id="1b562-103">Profilers using NGEN /Profile assemblies may crash profiled ASP.NET MVC4 applications on startup with a 'Fatal Execution Engine Exception'</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1b562-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="1b562-104">Suggestion</span></span>

<span data-ttu-id="1b562-105">Dieses Problem wurde in .NET Framework 4.5.2 behoben.</span><span class="sxs-lookup"><span data-stu-id="1b562-105">This issue is fixed in the .NET Framework 4.5.2.</span></span> <span data-ttu-id="1b562-106">Der Profiler kann das Problem jedoch umgehen, indem er <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in der Ereignismaske angibt.</span><span class="sxs-lookup"><span data-stu-id="1b562-106">Alternatively, the profiler may avoid this issue by specifying <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in its event mask.</span></span>

| <span data-ttu-id="1b562-107">name</span><span class="sxs-lookup"><span data-stu-id="1b562-107">Name</span></span>    | <span data-ttu-id="1b562-108">Wert</span><span class="sxs-lookup"><span data-stu-id="1b562-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1b562-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="1b562-109">Scope</span></span>   |<span data-ttu-id="1b562-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1b562-110">Edge</span></span>|
|<span data-ttu-id="1b562-111">Version</span><span class="sxs-lookup"><span data-stu-id="1b562-111">Version</span></span>|<span data-ttu-id="1b562-112">4.5</span><span class="sxs-lookup"><span data-stu-id="1b562-112">4.5</span></span>|
|<span data-ttu-id="1b562-113">Typ</span><span class="sxs-lookup"><span data-stu-id="1b562-113">Type</span></span>|<span data-ttu-id="1b562-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="1b562-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="1b562-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="1b562-115">Affected APIs</span></span>

<span data-ttu-id="1b562-116">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="1b562-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
