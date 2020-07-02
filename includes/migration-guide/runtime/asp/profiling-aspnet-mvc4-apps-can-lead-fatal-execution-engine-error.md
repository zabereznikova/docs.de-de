---
ms.openlocfilehash: 2e13268d4983af5d2fdd6d12b4d9e67d61d07f3d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622031"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a><span data-ttu-id="7f997-101">Bei der Profilerstellung für ASP.NET MVC4-Apps kann ein schwerwiegender Fehler der Ausführungs-Engine entstehen</span><span class="sxs-lookup"><span data-stu-id="7f997-101">Profiling ASP.Net MVC4 apps can lead to Fatal Execution Engine Error</span></span>

#### <a name="details"></a><span data-ttu-id="7f997-102">Details</span><span class="sxs-lookup"><span data-stu-id="7f997-102">Details</span></span>

<span data-ttu-id="7f997-103">Profiler, die NGEN- bzw. Profilassemblys verwenden, lösen möglicherweise beim Start von ASP.NET MVC4-Anwendungen mit Profilen einen „schwerwiegenden Fehler der Ausführungs-Engine“ aus</span><span class="sxs-lookup"><span data-stu-id="7f997-103">Profilers using NGEN /Profile assemblies may crash profiled ASP.NET MVC4 applications on startup with a 'Fatal Execution Engine Exception'</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7f997-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="7f997-104">Suggestion</span></span>

<span data-ttu-id="7f997-105">Dieses Problem wurde in .NET Framework 4.5.2 behoben.</span><span class="sxs-lookup"><span data-stu-id="7f997-105">This issue is fixed in the .NET Framework 4.5.2.</span></span> <span data-ttu-id="7f997-106">Der Profiler kann das Problem jedoch umgehen, indem er <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in der Ereignismaske angibt.</span><span class="sxs-lookup"><span data-stu-id="7f997-106">Alternatively, the profiler may avoid this issue by specifying <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in its event mask.</span></span>

| <span data-ttu-id="7f997-107">name</span><span class="sxs-lookup"><span data-stu-id="7f997-107">Name</span></span>    | <span data-ttu-id="7f997-108">Wert</span><span class="sxs-lookup"><span data-stu-id="7f997-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7f997-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="7f997-109">Scope</span></span>   |<span data-ttu-id="7f997-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7f997-110">Edge</span></span>|
|<span data-ttu-id="7f997-111">Version</span><span class="sxs-lookup"><span data-stu-id="7f997-111">Version</span></span>|<span data-ttu-id="7f997-112">4.5</span><span class="sxs-lookup"><span data-stu-id="7f997-112">4.5</span></span>|
|<span data-ttu-id="7f997-113">Typ</span><span class="sxs-lookup"><span data-stu-id="7f997-113">Type</span></span>|<span data-ttu-id="7f997-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="7f997-114">Runtime</span></span>|
