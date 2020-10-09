---
ms.openlocfilehash: 8b70df0fb2072fd5243d9e46a4a20c22cc7fd677
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "91607790"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a><span data-ttu-id="01c3f-101">Profilerstellung für ASP.NET MVC4-Apps kann zu schwerwiegendem Fehler der Ausführungs-Engine führen</span><span class="sxs-lookup"><span data-stu-id="01c3f-101">Profiling ASP.NET MVC4 apps can lead to Fatal Execution Engine Error</span></span>

#### <a name="details"></a><span data-ttu-id="01c3f-102">Details</span><span class="sxs-lookup"><span data-stu-id="01c3f-102">Details</span></span>

<span data-ttu-id="01c3f-103">Profiler, die NGEN- bzw. Profilassemblys verwenden, lösen möglicherweise beim Start von ASP.NET MVC4-Anwendungen mit Profilen einen „schwerwiegenden Fehler der Ausführungs-Engine“ aus</span><span class="sxs-lookup"><span data-stu-id="01c3f-103">Profilers using NGEN /Profile assemblies may crash profiled ASP.NET MVC4 applications on startup with a 'Fatal Execution Engine Exception'</span></span>

#### <a name="suggestion"></a><span data-ttu-id="01c3f-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="01c3f-104">Suggestion</span></span>

<span data-ttu-id="01c3f-105">Dieses Problem wurde in .NET Framework 4.5.2 behoben.</span><span class="sxs-lookup"><span data-stu-id="01c3f-105">This issue is fixed in the .NET Framework 4.5.2.</span></span> <span data-ttu-id="01c3f-106">Der Profiler kann das Problem jedoch umgehen, indem er <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in der Ereignismaske angibt.</span><span class="sxs-lookup"><span data-stu-id="01c3f-106">Alternatively, the profiler may avoid this issue by specifying <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in its event mask.</span></span>

| <span data-ttu-id="01c3f-107">name</span><span class="sxs-lookup"><span data-stu-id="01c3f-107">Name</span></span>    | <span data-ttu-id="01c3f-108">Wert</span><span class="sxs-lookup"><span data-stu-id="01c3f-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="01c3f-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="01c3f-109">Scope</span></span>   |<span data-ttu-id="01c3f-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="01c3f-110">Edge</span></span>|
|<span data-ttu-id="01c3f-111">Version</span><span class="sxs-lookup"><span data-stu-id="01c3f-111">Version</span></span>|<span data-ttu-id="01c3f-112">4.5</span><span class="sxs-lookup"><span data-stu-id="01c3f-112">4.5</span></span>|
|<span data-ttu-id="01c3f-113">Typ</span><span class="sxs-lookup"><span data-stu-id="01c3f-113">Type</span></span>|<span data-ttu-id="01c3f-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="01c3f-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="01c3f-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="01c3f-115">Affected APIs</span></span>

<span data-ttu-id="01c3f-116">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="01c3f-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
