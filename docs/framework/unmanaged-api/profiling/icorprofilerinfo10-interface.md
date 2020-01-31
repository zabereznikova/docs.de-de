---
title: ICorProfilerInfo10-Schnittstelle
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: e90a1ffbc037636e4296bbd4f4c3c5082885e9f3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863243"
---
# <a name="icorprofilerinfo10-interface"></a><span data-ttu-id="404ec-102">ICorProfilerInfo10-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="404ec-102">ICorProfilerInfo10 Interface</span></span>

<span data-ttu-id="404ec-103">Eine Unterklasse von [ICorProfilerInfo9](icorprofilerinfo9-interface.md) , die Methoden zum Ändern der Funktions-Il, zum Abfragen von Informationen von der Laufzeit sowie zum aussetzen und Fortsetzen der Laufzeit bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="404ec-103">A subclass of [ICorProfilerInfo9](icorprofilerinfo9-interface.md) that provides methods to modify function IL, query information from the runtime, and suspend and resume the runtime.</span></span>

## <a name="methods"></a><span data-ttu-id="404ec-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="404ec-104">Methods</span></span>  

| <span data-ttu-id="404ec-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="404ec-105">Method</span></span>|<span data-ttu-id="404ec-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="404ec-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="404ec-107">Enumerateobjectreferences-Methode</span><span class="sxs-lookup"><span data-stu-id="404ec-107">EnumerateObjectReferences Method</span></span>](icorprofilerinfo10-enumerateobjectreferences-method.md)|<span data-ttu-id="404ec-108">Bei Angabe von ObjectID, Callback und clientData listet alle Objekt Verweise auf (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="404ec-108">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span> |
|[<span data-ttu-id="404ec-109">Isfrozenobject-Methode</span><span class="sxs-lookup"><span data-stu-id="404ec-109">IsFrozenObject Method</span></span>](icorprofilerinfo10-isfrozenobject-method.md)|<span data-ttu-id="404ec-110">Bestimmt bei Angabe einer ObjectID, ob das Objekt ein Schreib geschütztes Segment ist.</span><span class="sxs-lookup"><span data-stu-id="404ec-110">Given an ObjectID, determines whether the object is in a read-only segment.</span></span> |
|[<span data-ttu-id="404ec-111">Getlohobjectsizethreshold-Methode</span><span class="sxs-lookup"><span data-stu-id="404ec-111">GetLOHObjectSizeThreshold Method</span></span>](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|<span data-ttu-id="404ec-112">Ruft den Wert des konfigurierten Loh-Schwellenwerts ab.</span><span class="sxs-lookup"><span data-stu-id="404ec-112">Gets the value of the configured LOH threshold.</span></span> |
|[<span data-ttu-id="404ec-113">Requestrejitwithinliners-Methode</span><span class="sxs-lookup"><span data-stu-id="404ec-113">RequestReJITWithInliners Method</span></span>](icorprofilerinfo10-requestrejitwithinliners-method.md)| <span data-ttu-id="404ec-114">Rejits die angeforderten Methoden sowie alle inlinder angeforderten Methoden.</span><span class="sxs-lookup"><span data-stu-id="404ec-114">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>  |
|[<span data-ttu-id="404ec-115">Suspendruntime-Methode</span><span class="sxs-lookup"><span data-stu-id="404ec-115">SuspendRuntime Method</span></span>](icorprofilerinfo10-suspendruntime-method.md)| <span data-ttu-id="404ec-116">Hält die Laufzeit an, ohne eine GC auszuführen.</span><span class="sxs-lookup"><span data-stu-id="404ec-116">Suspends the runtime without performing a GC.</span></span> |
|[<span data-ttu-id="404ec-117">Resumeruntime-Methode</span><span class="sxs-lookup"><span data-stu-id="404ec-117">ResumeRuntime Method</span></span>](icorprofilerinfo10-resumeruntime-method.md)| <span data-ttu-id="404ec-118">Setzt die Laufzeit fort, ohne eine GC auszuführen.</span><span class="sxs-lookup"><span data-stu-id="404ec-118">Resumes the runtime without performing a GC.</span></span> |

## <a name="requirements"></a><span data-ttu-id="404ec-119">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="404ec-119">Requirements</span></span>  
<span data-ttu-id="404ec-120">**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="404ec-120">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>  
<span data-ttu-id="404ec-121">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="404ec-121">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="404ec-122">**.NET-Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="404ec-122">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span> 

## <a name="see-also"></a><span data-ttu-id="404ec-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="404ec-123">See also</span></span>

- [<span data-ttu-id="404ec-124">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="404ec-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
