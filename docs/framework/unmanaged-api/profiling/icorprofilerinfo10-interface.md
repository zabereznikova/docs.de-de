---
title: ICorProfilerInfo10-Schnittstelle
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: a99fa8410bbd0dedeaeb9e1713107a3dcc9ada6b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727223"
---
# <a name="icorprofilerinfo10-interface"></a><span data-ttu-id="ecea3-102">ICorProfilerInfo10-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ecea3-102">ICorProfilerInfo10 Interface</span></span>

<span data-ttu-id="ecea3-103">Eine Unterklasse von [ICorProfilerInfo9](icorprofilerinfo9-interface.md) , die Methoden zum Ändern der Funktions-Il, zum Abfragen von Informationen von der Laufzeit sowie zum aussetzen und Fortsetzen der Laufzeit bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ecea3-103">A subclass of [ICorProfilerInfo9](icorprofilerinfo9-interface.md) that provides methods to modify function IL, query information from the runtime, and suspend and resume the runtime.</span></span>

## <a name="methods"></a><span data-ttu-id="ecea3-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ecea3-104">Methods</span></span>  

| <span data-ttu-id="ecea3-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ecea3-105">Method</span></span>|<span data-ttu-id="ecea3-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ecea3-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="ecea3-107">EnumerateObjectReferences-Methode</span><span class="sxs-lookup"><span data-stu-id="ecea3-107">EnumerateObjectReferences Method</span></span>](icorprofilerinfo10-enumerateobjectreferences-method.md)|<span data-ttu-id="ecea3-108">Bei Angabe von ObjectID, Callback und clientData listet alle Objekt Verweise auf (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="ecea3-108">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span> |
|[<span data-ttu-id="ecea3-109">IsFrozenObject-Methode</span><span class="sxs-lookup"><span data-stu-id="ecea3-109">IsFrozenObject Method</span></span>](icorprofilerinfo10-isfrozenobject-method.md)|<span data-ttu-id="ecea3-110">Bestimmt bei Angabe einer ObjectID, ob das Objekt ein Schreib geschütztes Segment ist.</span><span class="sxs-lookup"><span data-stu-id="ecea3-110">Given an ObjectID, determines whether the object is in a read-only segment.</span></span> |
|[<span data-ttu-id="ecea3-111">GetLOHObjectSizeThreshold-Methode</span><span class="sxs-lookup"><span data-stu-id="ecea3-111">GetLOHObjectSizeThreshold Method</span></span>](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|<span data-ttu-id="ecea3-112">Ruft den Wert des konfigurierten Loh-Schwellenwerts ab.</span><span class="sxs-lookup"><span data-stu-id="ecea3-112">Gets the value of the configured LOH threshold.</span></span> |
|[<span data-ttu-id="ecea3-113">RequestReJITWithInliners-Methode</span><span class="sxs-lookup"><span data-stu-id="ecea3-113">RequestReJITWithInliners Method</span></span>](icorprofilerinfo10-requestrejitwithinliners-method.md)| <span data-ttu-id="ecea3-114">Rejits die angeforderten Methoden sowie alle inlinder angeforderten Methoden.</span><span class="sxs-lookup"><span data-stu-id="ecea3-114">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>  |
|[<span data-ttu-id="ecea3-115">SuspendRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="ecea3-115">SuspendRuntime Method</span></span>](icorprofilerinfo10-suspendruntime-method.md)| <span data-ttu-id="ecea3-116">Hält die Laufzeit an, ohne eine GC auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ecea3-116">Suspends the runtime without performing a GC.</span></span> |
|[<span data-ttu-id="ecea3-117">ResumeRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="ecea3-117">ResumeRuntime Method</span></span>](icorprofilerinfo10-resumeruntime-method.md)| <span data-ttu-id="ecea3-118">Setzt die Laufzeit fort, ohne eine GC auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ecea3-118">Resumes the runtime without performing a GC.</span></span> |

## <a name="requirements"></a><span data-ttu-id="ecea3-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ecea3-119">Requirements</span></span>  

<span data-ttu-id="ecea3-120">**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="ecea3-120">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
<span data-ttu-id="ecea3-121">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ecea3-121">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="ecea3-122">**.NET-Versionen:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecea3-122">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ecea3-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ecea3-123">See also</span></span>

- [<span data-ttu-id="ecea3-124">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="ecea3-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
