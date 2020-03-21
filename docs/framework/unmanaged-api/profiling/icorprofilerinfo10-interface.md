---
title: ICorProfilerInfo10-Schnittstelle
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 4c5d553744008734037975d6e63e1b07b89cf886
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175069"
---
# <a name="icorprofilerinfo10-interface"></a><span data-ttu-id="8cfd1-102">ICorProfilerInfo10-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8cfd1-102">ICorProfilerInfo10 Interface</span></span>

<span data-ttu-id="8cfd1-103">Eine Unterklasse von [ICorProfilerInfo9,](icorprofilerinfo9-interface.md) die Methoden zum Ändern der Funktions-IL, Abfragen von Informationen aus der Laufzeit und Anhalten und Fortsetzen der Laufzeit bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="8cfd1-103">A subclass of [ICorProfilerInfo9](icorprofilerinfo9-interface.md) that provides methods to modify function IL, query information from the runtime, and suspend and resume the runtime.</span></span>

## <a name="methods"></a><span data-ttu-id="8cfd1-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="8cfd1-104">Methods</span></span>  

| <span data-ttu-id="8cfd1-105">Methode</span><span class="sxs-lookup"><span data-stu-id="8cfd1-105">Method</span></span>|<span data-ttu-id="8cfd1-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8cfd1-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="8cfd1-107">EnumerateObjectReferences-Methode</span><span class="sxs-lookup"><span data-stu-id="8cfd1-107">EnumerateObjectReferences Method</span></span>](icorprofilerinfo10-enumerateobjectreferences-method.md)|<span data-ttu-id="8cfd1-108">Zählt bei einer ObjectID, einem Rückruf und clientData jeder Objektverweis auf (falls vorhanden).</span><span class="sxs-lookup"><span data-stu-id="8cfd1-108">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span> |
|[<span data-ttu-id="8cfd1-109">IsFrozenObject-Methode</span><span class="sxs-lookup"><span data-stu-id="8cfd1-109">IsFrozenObject Method</span></span>](icorprofilerinfo10-isfrozenobject-method.md)|<span data-ttu-id="8cfd1-110">Bestimmt bei einer ObjectID, ob sich das Objekt in einem schreibgeschützten Segment befindet.</span><span class="sxs-lookup"><span data-stu-id="8cfd1-110">Given an ObjectID, determines whether the object is in a read-only segment.</span></span> |
|[<span data-ttu-id="8cfd1-111">GetLOHObjectSizeThreshold-Methode</span><span class="sxs-lookup"><span data-stu-id="8cfd1-111">GetLOHObjectSizeThreshold Method</span></span>](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|<span data-ttu-id="8cfd1-112">Ruft den Wert des konfigurierten LOH-Schwellenwerts ab.</span><span class="sxs-lookup"><span data-stu-id="8cfd1-112">Gets the value of the configured LOH threshold.</span></span> |
|[<span data-ttu-id="8cfd1-113">RequestReJITWithInliners-Methode</span><span class="sxs-lookup"><span data-stu-id="8cfd1-113">RequestReJITWithInliners Method</span></span>](icorprofilerinfo10-requestrejitwithinliners-method.md)| <span data-ttu-id="8cfd1-114">ReJITs die angeforderten Methoden sowie alle Inliner der angeforderten Methoden.</span><span class="sxs-lookup"><span data-stu-id="8cfd1-114">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>  |
|[<span data-ttu-id="8cfd1-115">SuspendRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="8cfd1-115">SuspendRuntime Method</span></span>](icorprofilerinfo10-suspendruntime-method.md)| <span data-ttu-id="8cfd1-116">Unterbricht die Laufzeit, ohne einen GC auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8cfd1-116">Suspends the runtime without performing a GC.</span></span> |
|[<span data-ttu-id="8cfd1-117">ResumeRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="8cfd1-117">ResumeRuntime Method</span></span>](icorprofilerinfo10-resumeruntime-method.md)| <span data-ttu-id="8cfd1-118">Setzt die Laufzeit fort, ohne einen GC auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8cfd1-118">Resumes the runtime without performing a GC.</span></span> |

## <a name="requirements"></a><span data-ttu-id="8cfd1-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8cfd1-119">Requirements</span></span>  
<span data-ttu-id="8cfd1-120">**Plattformen:** Siehe [.NET Core unterstützte Betriebssysteme](../../../core/install/dependencies.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="8cfd1-120">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>  
<span data-ttu-id="8cfd1-121">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8cfd1-121">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="8cfd1-122">**.NET-Versionen:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cfd1-122">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="8cfd1-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8cfd1-123">See also</span></span>

- [<span data-ttu-id="8cfd1-124">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="8cfd1-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
