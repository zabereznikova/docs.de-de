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
ms.openlocfilehash: add30952588ace0cbc80191617c37d7222cffee7
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864491"
---
# <a name="icorprofilerfunctionenum-interface"></a><span data-ttu-id="e7e28-102">ICorProfilerFunctionEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e7e28-102">ICorProfilerFunctionEnum Interface</span></span>
<span data-ttu-id="e7e28-103">Stellt Methoden bereit, um eine Auflistung von Funktionen in der CLR (Common Language Runtime) sequenziell zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="e7e28-103">Provides methods to sequentially iterate through a collection of functions in the common language runtime.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e7e28-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="e7e28-104">Methods</span></span>  
  
|<span data-ttu-id="e7e28-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="e7e28-105">Method</span></span>|<span data-ttu-id="e7e28-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e7e28-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e7e28-107">Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="e7e28-107">Clone Method</span></span>](icorprofilerfunctionenum-clone-method.md)|<span data-ttu-id="e7e28-108">Ruft einen Schnittstellenzeiger auf eine Kopie dieser `ICorProfilerFunctionEnum`-Schnittstelle ab.</span><span class="sxs-lookup"><span data-stu-id="e7e28-108">Gets an interface pointer to a copy of this `ICorProfilerFunctionEnum` interface.</span></span>|  
|[<span data-ttu-id="e7e28-109">GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="e7e28-109">GetCount Method</span></span>](icorprofilerfunctionenum-getcount-method.md)|<span data-ttu-id="e7e28-110">Ruft die Anzahl der Funktionen ab, die von der Anwendung oder erzwungen vom Profiler geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="e7e28-110">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>|  
|[<span data-ttu-id="e7e28-111">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="e7e28-111">Next Method</span></span>](icorprofilerfunctionenum-next-method.md)|<span data-ttu-id="e7e28-112">Ruft die angegebene Anzahl von zusammenhängenden Funktionen aus einer sequenziellen Auflistung von Funktionen ab und beginnt damit an der aktuellen Position des Enumerators in der Sequenz.</span><span class="sxs-lookup"><span data-stu-id="e7e28-112">Gets the specified number of contiguous functions from a sequential collection of functions, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="e7e28-113">Reset-Methode</span><span class="sxs-lookup"><span data-stu-id="e7e28-113">Reset Method</span></span>](icorprofilerfunctionenum-reset-method.md)|<span data-ttu-id="e7e28-114">Verschiebt den Cursor des Enumerators an die Anfangsposition der Sequenz.</span><span class="sxs-lookup"><span data-stu-id="e7e28-114">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="e7e28-115">Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="e7e28-115">Skip Method</span></span>](icorprofilerfunctionenum-skip-method.md)|<span data-ttu-id="e7e28-116">Verschiebt den Cursor des Enumerators so aus seiner aktuellen Position, dass die angegebene Anzahl von Elementen übersprungen wird.</span><span class="sxs-lookup"><span data-stu-id="e7e28-116">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7e28-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e7e28-117">Remarks</span></span>  
 <span data-ttu-id="e7e28-118">Die `ICorProfilerFunctionEnum`-Schnittstelle ist ein Enumerator.</span><span class="sxs-lookup"><span data-stu-id="e7e28-118">The `ICorProfilerFunctionEnum` interface is an enumerator.</span></span> <span data-ttu-id="e7e28-119">Hiermit kann der Empfänger eines Arrays mit einer Rate, die für den Empfänger geeignet ist, Elemente vom Absender abrufen.</span><span class="sxs-lookup"><span data-stu-id="e7e28-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="e7e28-120">Anders ausgedrückt: Der Empfänger kann explizit den Fluss der Arrayelemente steuern und auf diese Weise Probleme im Zusammenhang mit der Übergabe großer Arrays als Methodenparameter vermeiden.</span><span class="sxs-lookup"><span data-stu-id="e7e28-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
 <span data-ttu-id="e7e28-121">`ICorProfilerFunctionEnum` zählt Funktionen auf, die bereits mit JIT kompiliert wurden, jedoch keine Funktionen, die aus mit "Ngen.exe" generierten systemeigenen Images geladen werden.</span><span class="sxs-lookup"><span data-stu-id="e7e28-121">`ICorProfilerFunctionEnum` enumerates over functions that have already been JIT-compiled, but does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7e28-122">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e7e28-122">Requirements</span></span>  
 <span data-ttu-id="e7e28-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7e28-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7e28-124">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e7e28-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e7e28-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7e28-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7e28-126">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7e28-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7e28-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7e28-127">See also</span></span>

- [<span data-ttu-id="e7e28-128">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e7e28-128">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="e7e28-129">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="e7e28-129">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="e7e28-130">EnumJITedFunctions-Methode</span><span class="sxs-lookup"><span data-stu-id="e7e28-130">EnumJITedFunctions Method</span></span>](icorprofilerinfo3-enumjitedfunctions-method.md)
