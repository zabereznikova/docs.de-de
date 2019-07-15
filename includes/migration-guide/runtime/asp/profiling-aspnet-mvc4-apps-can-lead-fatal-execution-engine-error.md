---
ms.openlocfilehash: 107b34c7bd26e1396e8a6638d6929c15de92b8e4
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67803182"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a><span data-ttu-id="3fe2a-101">Bei der Profilerstellung für ASP.NET MVC4-Apps kann ein schwerwiegender Fehler der Ausführungs-Engine entstehen</span><span class="sxs-lookup"><span data-stu-id="3fe2a-101">Profiling ASP.Net MVC4 apps can lead to Fatal Execution Engine Error</span></span>

|   |   |
|---|---|
|<span data-ttu-id="3fe2a-102">Details</span><span class="sxs-lookup"><span data-stu-id="3fe2a-102">Details</span></span>|<span data-ttu-id="3fe2a-103">Profiler, die NGEN- bzw. Profilassemblys verwenden, lösen möglicherweise beim Start von ASP.NET MVC4-Anwendungen mit Profilen einen „schwerwiegenden Fehler der Ausführungs-Engine“ aus</span><span class="sxs-lookup"><span data-stu-id="3fe2a-103">Profilers using NGEN /Profile assemblies may crash profiled ASP.NET MVC4 applications on startup with a 'Fatal Execution Engine Exception'</span></span>|
|<span data-ttu-id="3fe2a-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="3fe2a-104">Suggestion</span></span>|<span data-ttu-id="3fe2a-105">Dieses Problem wurde in .NET Framework 4.5.2 behoben.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-105">This issue is fixed in the .NET Framework 4.5.2.</span></span> <span data-ttu-id="3fe2a-106">Der Profiler kann das Problem jedoch umgehen, indem er <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in der Ereignismaske angibt.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-106">Alternatively, the profiler may avoid this issue by specifying <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in its event mask.</span></span>|
|<span data-ttu-id="3fe2a-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="3fe2a-107">Scope</span></span>|<span data-ttu-id="3fe2a-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3fe2a-108">Edge</span></span>|
|<span data-ttu-id="3fe2a-109">Version</span><span class="sxs-lookup"><span data-stu-id="3fe2a-109">Version</span></span>|<span data-ttu-id="3fe2a-110">4.5</span><span class="sxs-lookup"><span data-stu-id="3fe2a-110">4.5</span></span>|
|<span data-ttu-id="3fe2a-111">Typ</span><span class="sxs-lookup"><span data-stu-id="3fe2a-111">Type</span></span>|<span data-ttu-id="3fe2a-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="3fe2a-112">Runtime</span></span>|

