---
ms.openlocfilehash: 4f52535e54607cc824500f9c6a14964a1dec9d32
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620212"
---
### <a name="cor_prf_gc_root_handles-are-not-being-enumerated-by-profilers"></a><span data-ttu-id="d599f-101">COR_PRF_GC_ROOT_HANDLE-Elemente werden nicht vom Profiler aufgezählt</span><span class="sxs-lookup"><span data-stu-id="d599f-101">COR_PRF_GC_ROOT_HANDLEs are not being enumerated by profilers</span></span>

#### <a name="details"></a><span data-ttu-id="d599f-102">Details</span><span class="sxs-lookup"><span data-stu-id="d599f-102">Details</span></span>

<span data-ttu-id="d599f-103">In .NET Framework 4.5.1 gibt die Profilerstellungs-API <code>RootReferences2()</code> fälschlicherweise nie <code>COR_PRF_GC_ROOT_HANDLE</code> zurück (stattdessen wird <code>COR_PRF_GC_ROOT_OTHER</code> zurückgegeben).</span><span class="sxs-lookup"><span data-stu-id="d599f-103">In the .NET Framework v4.5.1, the profiling API <code>RootReferences2()</code> is incorrectly never returning <code>COR_PRF_GC_ROOT_HANDLE</code> (they are returned as <code>COR_PRF_GC_ROOT_OTHER</code> instead).</span></span> <span data-ttu-id="d599f-104">Dieses Problem ist seit .NET Framework 4.6 behoben.</span><span class="sxs-lookup"><span data-stu-id="d599f-104">This issue is fixed beginning in the .NET Framework 4.6.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d599f-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="d599f-105">Suggestion</span></span>

<span data-ttu-id="d599f-106">Dieses Problem wurde in .NET Framework 4.6 behoben und kann durch ein Upgrade auf diese Version von .NET Framework vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="d599f-106">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="d599f-107">name</span><span class="sxs-lookup"><span data-stu-id="d599f-107">Name</span></span>    | <span data-ttu-id="d599f-108">Wert</span><span class="sxs-lookup"><span data-stu-id="d599f-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d599f-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="d599f-109">Scope</span></span>   |<span data-ttu-id="d599f-110">Gering</span><span class="sxs-lookup"><span data-stu-id="d599f-110">Minor</span></span>|
|<span data-ttu-id="d599f-111">Version</span><span class="sxs-lookup"><span data-stu-id="d599f-111">Version</span></span>|<span data-ttu-id="d599f-112">4.5.1</span><span class="sxs-lookup"><span data-stu-id="d599f-112">4.5.1</span></span>|
|<span data-ttu-id="d599f-113">Typ</span><span class="sxs-lookup"><span data-stu-id="d599f-113">Type</span></span>|<span data-ttu-id="d599f-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="d599f-114">Runtime</span></span>|
