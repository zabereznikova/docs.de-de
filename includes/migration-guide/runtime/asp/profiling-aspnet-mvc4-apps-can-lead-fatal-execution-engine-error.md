---
ms.openlocfilehash: 439a4976482639cd2e4e17315ec1a53ca54aa477
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803182"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a><span data-ttu-id="ff9f3-101">Bei der Profilerstellung für ASP.NET MVC4-Apps kann ein schwerwiegender Fehler der Ausführungs-Engine entstehen</span><span class="sxs-lookup"><span data-stu-id="ff9f3-101">Profiling ASP.Net MVC4 apps can lead to Fatal Execution Engine Error</span></span>

|   |   |
|---|---|
|<span data-ttu-id="ff9f3-102">Details</span><span class="sxs-lookup"><span data-stu-id="ff9f3-102">Details</span></span>|<span data-ttu-id="ff9f3-103">Profiler, die NGEN- bzw. Profilassemblys verwenden, lösen möglicherweise beim Start von ASP.NET MVC4-Anwendungen mit Profilen einen „schwerwiegenden Fehler der Ausführungs-Engine“ aus</span><span class="sxs-lookup"><span data-stu-id="ff9f3-103">Profilers using NGEN /Profile assemblies may crash profiled ASP.NET MVC4 applications on startup with a 'Fatal Execution Engine Exception'</span></span>|
|<span data-ttu-id="ff9f3-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="ff9f3-104">Suggestion</span></span>|<span data-ttu-id="ff9f3-105">Dieses Problem wurde in .NET Framework 4.5.2 behoben.</span><span class="sxs-lookup"><span data-stu-id="ff9f3-105">This issue is fixed in the .NET Framework 4.5.2.</span></span> <span data-ttu-id="ff9f3-106">Der Profiler kann das Problem jedoch umgehen, indem er <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in der Ereignismaske angibt.</span><span class="sxs-lookup"><span data-stu-id="ff9f3-106">Alternatively, the profiler may avoid this issue by specifying <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in its event mask.</span></span>|
|<span data-ttu-id="ff9f3-107">`Scope`</span><span class="sxs-lookup"><span data-stu-id="ff9f3-107">Scope</span></span>|<span data-ttu-id="ff9f3-108">Edge</span><span class="sxs-lookup"><span data-stu-id="ff9f3-108">Edge</span></span>|
|<span data-ttu-id="ff9f3-109">Version</span><span class="sxs-lookup"><span data-stu-id="ff9f3-109">Version</span></span>|<span data-ttu-id="ff9f3-110">4.5</span><span class="sxs-lookup"><span data-stu-id="ff9f3-110">4.5</span></span>|
|<span data-ttu-id="ff9f3-111">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="ff9f3-111">Type</span></span>|<span data-ttu-id="ff9f3-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="ff9f3-112">Runtime</span></span>|
