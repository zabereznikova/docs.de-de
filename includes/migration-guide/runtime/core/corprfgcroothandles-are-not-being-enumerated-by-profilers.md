---
ms.openlocfilehash: 8dc98b2d9c2c0b5f145ebce48cf8f5e054975c6e
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858383"
---
### <a name="corprfgcroothandles-are-not-being-enumerated-by-profilers"></a><span data-ttu-id="34012-101">COR_PRF_GC_ROOT_HANDLE-Elemente werden nicht vom Profiler aufgezählt</span><span class="sxs-lookup"><span data-stu-id="34012-101">COR_PRF_GC_ROOT_HANDLEs are not being enumerated by profilers</span></span>

|   |   |
|---|---|
|<span data-ttu-id="34012-102">Details</span><span class="sxs-lookup"><span data-stu-id="34012-102">Details</span></span>|<span data-ttu-id="34012-103">In .NET Framework 4.5.1 gibt die Profilerstellungs-API <code>RootReferences2()</code> fälschlicherweise nie <code>COR_PRF_GC_ROOT_HANDLE</code> zurück (stattdessen wird <code>COR_PRF_GC_ROOT_OTHER</code> zurückgegeben).</span><span class="sxs-lookup"><span data-stu-id="34012-103">In the .NET Framework v4.5.1, the profiling API <code>RootReferences2()</code> is incorrectly never returning <code>COR_PRF_GC_ROOT_HANDLE</code> (they are returned as <code>COR_PRF_GC_ROOT_OTHER</code> instead).</span></span> <span data-ttu-id="34012-104">Dieses Problem ist seit .NET Framework 4.6 behoben.</span><span class="sxs-lookup"><span data-stu-id="34012-104">This issue is fixed beginning in the .NET Framework 4.6.</span></span>|
|<span data-ttu-id="34012-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="34012-105">Suggestion</span></span>|<span data-ttu-id="34012-106">Dieses Problem wurde in .NET Framework 4.6 behoben und kann durch ein Upgrade auf diese Version von .NET Framework vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="34012-106">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>|
|<span data-ttu-id="34012-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="34012-107">Scope</span></span>|<span data-ttu-id="34012-108">Gering</span><span class="sxs-lookup"><span data-stu-id="34012-108">Minor</span></span>|
|<span data-ttu-id="34012-109">Version</span><span class="sxs-lookup"><span data-stu-id="34012-109">Version</span></span>|<span data-ttu-id="34012-110">4.5.1</span><span class="sxs-lookup"><span data-stu-id="34012-110">4.5.1</span></span>|
|<span data-ttu-id="34012-111">Typ</span><span class="sxs-lookup"><span data-stu-id="34012-111">Type</span></span>|<span data-ttu-id="34012-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="34012-112">Runtime</span></span>|

