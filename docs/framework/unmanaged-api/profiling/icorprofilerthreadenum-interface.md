---
title: ICorProfilerThreadEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum
helpviewer_keywords:
- ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: 1e35031b-e095-4c14-9644-8deeb3081e0b
topic_type:
- apiref
ms.openlocfilehash: d28991254fba73de7a55135844d16417580d8792
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84494383"
---
# <a name="icorprofilerthreadenum-interface"></a><span data-ttu-id="b805e-102">ICorProfilerThreadEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b805e-102">ICorProfilerThreadEnum Interface</span></span>
<span data-ttu-id="b805e-103">Stellt Methoden bereit, um eine Auflistung von Threads in der CLR (Common Language Runtime) sequenziell zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="b805e-103">Provides methods to sequentially iterate through a collection of threads in the common language runtime.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b805e-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="b805e-104">Methods</span></span>  
  
|<span data-ttu-id="b805e-105">Methode</span><span class="sxs-lookup"><span data-stu-id="b805e-105">Method</span></span>|<span data-ttu-id="b805e-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b805e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b805e-107">Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="b805e-107">Clone Method</span></span>](icorprofilerthreadenum-clone-method.md)|<span data-ttu-id="b805e-108">Ruft einen Schnittstellenzeiger auf eine Kopie dieser `ICorProfilerThreadEnum`-Schnittstelle ab.</span><span class="sxs-lookup"><span data-stu-id="b805e-108">Gets an interface pointer to a copy of this `ICorProfilerThreadEnum` interface.</span></span>|  
|[<span data-ttu-id="b805e-109">GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="b805e-109">GetCount Method</span></span>](icorprofilerthreadenum-getcount-method.md)|<span data-ttu-id="b805e-110">Ruft die Anzahl der Threads ab, die von der Anwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b805e-110">Gets the number of threads that are used by the application.</span></span>|  
|[<span data-ttu-id="b805e-111">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="b805e-111">Next Method</span></span>](icorprofilerthreadenum-next-method.md)|<span data-ttu-id="b805e-112">Ruft die angegebene Anzahl von zusammenhängenden Threads aus einer sequenziellen Auflistung von Threads ab der Position ab, die der Enumerator aktuell in der Sequenz hat.</span><span class="sxs-lookup"><span data-stu-id="b805e-112">Gets the specified number of contiguous threads from a sequential collection of threads, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="b805e-113">Reset-Methode</span><span class="sxs-lookup"><span data-stu-id="b805e-113">Reset Method</span></span>](icorprofilerthreadenum-reset-method.md)|<span data-ttu-id="b805e-114">Verschiebt den Cursor des Enumerators an die Anfangsposition der Sequenz.</span><span class="sxs-lookup"><span data-stu-id="b805e-114">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="b805e-115">Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="b805e-115">Skip Method</span></span>](icorprofilerthreadenum-skip-method.md)|<span data-ttu-id="b805e-116">Verschiebt den Cursor des Enumerators so aus seiner aktuellen Position, dass die angegebene Anzahl von Elementen übersprungen wird.</span><span class="sxs-lookup"><span data-stu-id="b805e-116">Advances the enumerator's cursor from its current position to skip the specified number of elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b805e-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b805e-117">Remarks</span></span>  
 <span data-ttu-id="b805e-118">Die `ICorProfilerThreadEnum`-Schnittstelle ist ein Enumerator.</span><span class="sxs-lookup"><span data-stu-id="b805e-118">The `ICorProfilerThreadEnum` interface is an enumerator.</span></span> <span data-ttu-id="b805e-119">Hiermit kann der Empfänger eines Arrays mit einer Rate, die für den Empfänger geeignet ist, Elemente vom Absender abrufen.</span><span class="sxs-lookup"><span data-stu-id="b805e-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="b805e-120">Anders ausgedrückt: Der Empfänger kann explizit den Fluss der Arrayelemente steuern und auf diese Weise Probleme im Zusammenhang mit der Übergabe großer Arrays als Methodenparameter vermeiden.</span><span class="sxs-lookup"><span data-stu-id="b805e-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b805e-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b805e-121">Requirements</span></span>  
 <span data-ttu-id="b805e-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b805e-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b805e-123">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b805e-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b805e-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b805e-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b805e-125">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b805e-125">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b805e-126">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="b805e-126">See also</span></span>

- [<span data-ttu-id="b805e-127">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b805e-127">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="b805e-128">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="b805e-128">Profiling Interfaces</span></span>](profiling-interfaces.md)
