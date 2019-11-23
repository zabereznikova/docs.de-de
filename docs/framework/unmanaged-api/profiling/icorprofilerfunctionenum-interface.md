---
title: ICorProfilerFunctionEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum
helpviewer_keywords:
- ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0a1d4a38-cd0b-4231-91df-13646218ae72
topic_type:
- apiref
ms.openlocfilehash: 17f7243096b7ac18e456f8f31196055492015346
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447799"
---
# <a name="icorprofilerfunctionenum-interface"></a><span data-ttu-id="a8e0f-102">ICorProfilerFunctionEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a8e0f-102">ICorProfilerFunctionEnum Interface</span></span>
<span data-ttu-id="a8e0f-103">Stellt Methoden bereit, um eine Auflistung von Funktionen in der CLR (Common Language Runtime) sequenziell zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="a8e0f-103">Provides methods to sequentially iterate through a collection of functions in the common language runtime.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a8e0f-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="a8e0f-104">Methods</span></span>  
  
|<span data-ttu-id="a8e0f-105">Methode</span><span class="sxs-lookup"><span data-stu-id="a8e0f-105">Method</span></span>|<span data-ttu-id="a8e0f-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a8e0f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a8e0f-107">Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="a8e0f-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-clone-method.md)|<span data-ttu-id="a8e0f-108">Ruft einen Schnittstellenzeiger auf eine Kopie dieser `ICorProfilerFunctionEnum`-Schnittstelle ab.</span><span class="sxs-lookup"><span data-stu-id="a8e0f-108">Gets an interface pointer to a copy of this `ICorProfilerFunctionEnum` interface.</span></span>|  
|[<span data-ttu-id="a8e0f-109">GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="a8e0f-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-getcount-method.md)|<span data-ttu-id="a8e0f-110">Ruft die Anzahl der Funktionen ab, die von der Anwendung oder erzwungen vom Profiler geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="a8e0f-110">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>|  
|[<span data-ttu-id="a8e0f-111">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="a8e0f-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-next-method.md)|<span data-ttu-id="a8e0f-112">Ruft die angegebene Anzahl von zusammenhängenden Funktionen aus einer sequenziellen Auflistung von Funktionen ab und beginnt damit an der aktuellen Position des Enumerators in der Sequenz.</span><span class="sxs-lookup"><span data-stu-id="a8e0f-112">Gets the specified number of contiguous functions from a sequential collection of functions, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="a8e0f-113">Reset-Methode</span><span class="sxs-lookup"><span data-stu-id="a8e0f-113">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-reset-method.md)|<span data-ttu-id="a8e0f-114">Verschiebt den Cursor des Enumerators an die Anfangsposition der Sequenz.</span><span class="sxs-lookup"><span data-stu-id="a8e0f-114">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="a8e0f-115">Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="a8e0f-115">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-skip-method.md)|<span data-ttu-id="a8e0f-116">Verschiebt den Cursor des Enumerators so aus seiner aktuellen Position, dass die angegebene Anzahl von Elementen übersprungen wird.</span><span class="sxs-lookup"><span data-stu-id="a8e0f-116">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8e0f-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a8e0f-117">Remarks</span></span>  
 <span data-ttu-id="a8e0f-118">Die `ICorProfilerFunctionEnum`-Schnittstelle ist ein Enumerator.</span><span class="sxs-lookup"><span data-stu-id="a8e0f-118">The `ICorProfilerFunctionEnum` interface is an enumerator.</span></span> <span data-ttu-id="a8e0f-119">Hiermit kann der Empfänger eines Arrays mit einer Rate, die für den Empfänger geeignet ist, Elemente vom Absender abrufen.</span><span class="sxs-lookup"><span data-stu-id="a8e0f-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="a8e0f-120">Anders ausgedrückt: Der Empfänger kann explizit den Fluss der Arrayelemente steuern und auf diese Weise Probleme im Zusammenhang mit der Übergabe großer Arrays als Methodenparameter vermeiden.</span><span class="sxs-lookup"><span data-stu-id="a8e0f-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
 <span data-ttu-id="a8e0f-121">`ICorProfilerFunctionEnum` zählt Funktionen auf, die bereits mit JIT kompiliert wurden, jedoch keine Funktionen, die aus mit "Ngen.exe" generierten systemeigenen Images geladen werden.</span><span class="sxs-lookup"><span data-stu-id="a8e0f-121">`ICorProfilerFunctionEnum` enumerates over functions that have already been JIT-compiled, but does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8e0f-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a8e0f-122">Requirements</span></span>  
 <span data-ttu-id="a8e0f-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8e0f-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8e0f-124">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a8e0f-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a8e0f-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8e0f-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8e0f-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8e0f-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8e0f-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8e0f-127">See also</span></span>

- [<span data-ttu-id="a8e0f-128">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a8e0f-128">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="a8e0f-129">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="a8e0f-129">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="a8e0f-130">EnumJITedFunctions-Methode</span><span class="sxs-lookup"><span data-stu-id="a8e0f-130">EnumJITedFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)
