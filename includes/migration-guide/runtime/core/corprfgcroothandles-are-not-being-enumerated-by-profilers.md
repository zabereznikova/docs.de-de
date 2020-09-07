---
ms.openlocfilehash: 25437dcc0c814ed2265b2efb34316af48b372ebd
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497171"
---
### <a name="cor_prf_gc_root_handles-are-not-being-enumerated-by-profilers"></a><span data-ttu-id="52dda-101">COR_PRF_GC_ROOT_HANDLE-Elemente werden nicht vom Profiler aufgezählt</span><span class="sxs-lookup"><span data-stu-id="52dda-101">COR_PRF_GC_ROOT_HANDLEs are not being enumerated by profilers</span></span>

#### <a name="details"></a><span data-ttu-id="52dda-102">Details</span><span class="sxs-lookup"><span data-stu-id="52dda-102">Details</span></span>

<span data-ttu-id="52dda-103">In .NET Framework 4.5.1 gibt die Profilerstellungs-API <code>RootReferences2()</code> fälschlicherweise nie <code>COR_PRF_GC_ROOT_HANDLE</code> zurück (stattdessen wird <code>COR_PRF_GC_ROOT_OTHER</code> zurückgegeben).</span><span class="sxs-lookup"><span data-stu-id="52dda-103">In the .NET Framework v4.5.1, the profiling API <code>RootReferences2()</code> is incorrectly never returning <code>COR_PRF_GC_ROOT_HANDLE</code> (they are returned as <code>COR_PRF_GC_ROOT_OTHER</code> instead).</span></span> <span data-ttu-id="52dda-104">Dieses Problem ist seit .NET Framework 4.6 behoben.</span><span class="sxs-lookup"><span data-stu-id="52dda-104">This issue is fixed beginning in the .NET Framework 4.6.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="52dda-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="52dda-105">Suggestion</span></span>

<span data-ttu-id="52dda-106">Dieses Problem wurde in .NET Framework 4.6 behoben und kann durch ein Upgrade auf diese Version von .NET Framework vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="52dda-106">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="52dda-107">name</span><span class="sxs-lookup"><span data-stu-id="52dda-107">Name</span></span>    | <span data-ttu-id="52dda-108">Wert</span><span class="sxs-lookup"><span data-stu-id="52dda-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="52dda-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="52dda-109">Scope</span></span>   |<span data-ttu-id="52dda-110">Gering</span><span class="sxs-lookup"><span data-stu-id="52dda-110">Minor</span></span>|
|<span data-ttu-id="52dda-111">Version</span><span class="sxs-lookup"><span data-stu-id="52dda-111">Version</span></span>|<span data-ttu-id="52dda-112">4.5.1</span><span class="sxs-lookup"><span data-stu-id="52dda-112">4.5.1</span></span>|
|<span data-ttu-id="52dda-113">Typ</span><span class="sxs-lookup"><span data-stu-id="52dda-113">Type</span></span>|<span data-ttu-id="52dda-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="52dda-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="52dda-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="52dda-115">Affected APIs</span></span>

<span data-ttu-id="52dda-116">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="52dda-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
