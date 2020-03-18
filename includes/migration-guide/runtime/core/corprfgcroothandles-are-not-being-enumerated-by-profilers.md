---
ms.openlocfilehash: 8433899058c6f569e380999800557dbe8ed0a169
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858383"
---
### <a name="cor_prf_gc_root_handles-are-not-being-enumerated-by-profilers"></a><span data-ttu-id="a3b0f-101">COR_PRF_GC_ROOT_HANDLE-Elemente werden nicht vom Profiler aufgezählt</span><span class="sxs-lookup"><span data-stu-id="a3b0f-101">COR_PRF_GC_ROOT_HANDLEs are not being enumerated by profilers</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a3b0f-102">Details</span><span class="sxs-lookup"><span data-stu-id="a3b0f-102">Details</span></span>|<span data-ttu-id="a3b0f-103">In .NET Framework 4.5.1 gibt die Profilerstellungs-API <code>RootReferences2()</code> fälschlicherweise nie <code>COR_PRF_GC_ROOT_HANDLE</code> zurück (stattdessen wird <code>COR_PRF_GC_ROOT_OTHER</code> zurückgegeben).</span><span class="sxs-lookup"><span data-stu-id="a3b0f-103">In the .NET Framework v4.5.1, the profiling API <code>RootReferences2()</code> is incorrectly never returning <code>COR_PRF_GC_ROOT_HANDLE</code> (they are returned as <code>COR_PRF_GC_ROOT_OTHER</code> instead).</span></span> <span data-ttu-id="a3b0f-104">Dieses Problem ist seit .NET Framework 4.6 behoben.</span><span class="sxs-lookup"><span data-stu-id="a3b0f-104">This issue is fixed beginning in the .NET Framework 4.6.</span></span>|
|<span data-ttu-id="a3b0f-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="a3b0f-105">Suggestion</span></span>|<span data-ttu-id="a3b0f-106">Dieses Problem wurde in .NET Framework 4.6 behoben und kann durch ein Upgrade auf diese Version von .NET Framework vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="a3b0f-106">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>|
|<span data-ttu-id="a3b0f-107">`Scope`</span><span class="sxs-lookup"><span data-stu-id="a3b0f-107">Scope</span></span>|<span data-ttu-id="a3b0f-108">Nebenversion</span><span class="sxs-lookup"><span data-stu-id="a3b0f-108">Minor</span></span>|
|<span data-ttu-id="a3b0f-109">Version</span><span class="sxs-lookup"><span data-stu-id="a3b0f-109">Version</span></span>|<span data-ttu-id="a3b0f-110">4.5.1</span><span class="sxs-lookup"><span data-stu-id="a3b0f-110">4.5.1</span></span>|
|<span data-ttu-id="a3b0f-111">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a3b0f-111">Type</span></span>|<span data-ttu-id="a3b0f-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="a3b0f-112">Runtime</span></span>|
