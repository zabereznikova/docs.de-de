---
title: ICorProfilerInfo10-Schnittstelle
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: f2bc716110c14972e5b2c32bceb3123b16e87c61
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449842"
---
# <a name="icorprofilerinfo10-interface"></a><span data-ttu-id="d3e63-102">ICorProfilerInfo10-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d3e63-102">ICorProfilerInfo10 Interface</span></span>

<span data-ttu-id="d3e63-103">Eine Unterklasse von [ICorProfilerInfo9](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md) , die Methoden zum Ändern der Funktions-Il, zum Abfragen von Informationen von der Laufzeit sowie zum aussetzen und Fortsetzen der Laufzeit bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="d3e63-103">A subclass of [ICorProfilerInfo9](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md) that provides methods to modify function IL, query information from the runtime, and suspend and resume the runtime.</span></span>

## <a name="methods"></a><span data-ttu-id="d3e63-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="d3e63-104">Methods</span></span>  

| <span data-ttu-id="d3e63-105">Methode</span><span class="sxs-lookup"><span data-stu-id="d3e63-105">Method</span></span>|<span data-ttu-id="d3e63-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d3e63-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="d3e63-107">Enumerateobjectreferences-Methode</span><span class="sxs-lookup"><span data-stu-id="d3e63-107">EnumerateObjectReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-enumerateobjectreferences-method.md)|<span data-ttu-id="d3e63-108">Bei Angabe von ObjectID, Callback und clientData listet alle Objekt Verweise auf (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="d3e63-108">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span> |
|[<span data-ttu-id="d3e63-109">Isfrozenobject-Methode</span><span class="sxs-lookup"><span data-stu-id="d3e63-109">IsFrozenObject Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-isfrozenobject-method.md)|<span data-ttu-id="d3e63-110">Bestimmt bei Angabe einer ObjectID, ob das Objekt ein Schreib geschütztes Segment ist.</span><span class="sxs-lookup"><span data-stu-id="d3e63-110">Given an ObjectID, determines whether the object is in a read-only segment.</span></span> |
|[<span data-ttu-id="d3e63-111">Getlohobjectsizethreshold-Methode</span><span class="sxs-lookup"><span data-stu-id="d3e63-111">GetLOHObjectSizeThreshold Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-getlohobjectsizethreshold-method.md)|<span data-ttu-id="d3e63-112">Ruft den Wert des konfigurierten Loh-Schwellenwerts ab.</span><span class="sxs-lookup"><span data-stu-id="d3e63-112">Gets the value of the configured LOH threshold.</span></span> |
|[<span data-ttu-id="d3e63-113">Requestrejitwithinliners-Methode</span><span class="sxs-lookup"><span data-stu-id="d3e63-113">RequestReJITWithInliners Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-requestrejitwithinliners-method.md)| <span data-ttu-id="d3e63-114">Rejits die angeforderten Methoden sowie alle inlinder angeforderten Methoden.</span><span class="sxs-lookup"><span data-stu-id="d3e63-114">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>  |
|[<span data-ttu-id="d3e63-115">Suspendruntime-Methode</span><span class="sxs-lookup"><span data-stu-id="d3e63-115">SuspendRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-suspendruntime-method.md)| <span data-ttu-id="d3e63-116">Hält die Laufzeit an, ohne eine GC auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d3e63-116">Suspends the runtime without performing a GC.</span></span> |
|[<span data-ttu-id="d3e63-117">Resumeruntime-Methode</span><span class="sxs-lookup"><span data-stu-id="d3e63-117">ResumeRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-resumeruntime-method.md)| <span data-ttu-id="d3e63-118">Setzt die Laufzeit fort, ohne eine GC auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d3e63-118">Resumes the runtime without performing a GC.</span></span> |

## <a name="requirements"></a><span data-ttu-id="d3e63-119">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="d3e63-119">Requirements</span></span>  
<span data-ttu-id="d3e63-120">**Plattformen:** Siehe [unterstützte .net Core-Betriebssysteme](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="d3e63-120">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>  
<span data-ttu-id="d3e63-121">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d3e63-121">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="d3e63-122">**.NET-Versionen:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3e63-122">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span> 

## <a name="see-also"></a><span data-ttu-id="d3e63-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3e63-123">See also</span></span>

- [<span data-ttu-id="d3e63-124">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="d3e63-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
