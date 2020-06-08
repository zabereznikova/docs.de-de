---
title: ICorProfilerInfo4-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4
helpviewer_keywords:
- ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 80a5308e-c22f-4201-ba89-31cc8562515b
topic_type:
- apiref
ms.openlocfilehash: 58d11e9084f53c69f2656b4f0ee6bc7d2cc4ae21
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495865"
---
# <a name="icorprofilerinfo4-interface"></a><span data-ttu-id="67c63-102">ICorProfilerInfo4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="67c63-102">ICorProfilerInfo4 Interface</span></span>
<span data-ttu-id="67c63-103">Stellt Methoden bereit, die Code Profiler für die Kommunikation mit dem Common Language Runtime (CLR) verwenden, um die Ereignisüberwachung und Anforderungs Informationen zu steuern.</span><span class="sxs-lookup"><span data-stu-id="67c63-103">Provides methods that code profilers use to communicate with the common language runtime (CLR) to control event monitoring and request information.</span></span> <span data-ttu-id="67c63-104">.</span><span class="sxs-lookup"><span data-stu-id="67c63-104">.</span></span> <span data-ttu-id="67c63-105">Die- `ICorProfilerInfo4` Schnittstelle ist eine Erweiterung der anderen `ICorProfilerInfo` Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="67c63-105">The `ICorProfilerInfo4` interface is an extension of the other `ICorProfilerInfo` interfaces.</span></span> <span data-ttu-id="67c63-106">Es bietet neue Methoden zur Unterstützung der JIT-Neukompilierung (Just-in-Time), die in der .NET Framework 4,5 hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="67c63-106">It provides new methods to support just-in-time (JIT) recompilation, added in the .NET Framework 4.5.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="67c63-107">Methoden</span><span class="sxs-lookup"><span data-stu-id="67c63-107">Methods</span></span>  
  
|<span data-ttu-id="67c63-108">Methode</span><span class="sxs-lookup"><span data-stu-id="67c63-108">Method</span></span>|<span data-ttu-id="67c63-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="67c63-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="67c63-110">EnumJITedFunctions2-Methode</span><span class="sxs-lookup"><span data-stu-id="67c63-110">EnumJITedFunctions2 Method</span></span>](icorprofilerinfo4-enumjitedfunctions2-method.md)|<span data-ttu-id="67c63-111">Gibt einen Enumerator für alle Funktionen zurück, die zuvor JIT-kompiliert und JIT-neu kompiliert wurden.</span><span class="sxs-lookup"><span data-stu-id="67c63-111">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span>|  
|[<span data-ttu-id="67c63-112">EnumThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="67c63-112">EnumThreads Method</span></span>](icorprofilerinfo4-enumthreads-method.md)|<span data-ttu-id="67c63-113">Ruft einen Enumerator ab, der Methoden zum sequenziellen durchlaufen der Auflistung aller verwalteten Threads im Profil Erstellungs Prozess bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="67c63-113">Gets an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>|  
|[<span data-ttu-id="67c63-114">GetCodeInfo3-Methode</span><span class="sxs-lookup"><span data-stu-id="67c63-114">GetCodeInfo3 Method</span></span>](icorprofilerinfo4-getcodeinfo3-method.md)|<span data-ttu-id="67c63-115">Ruft die Erweiterungen des systemeigenen Codes ab, die der JIT-kompilierten Version der angegebenen Funktion zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="67c63-115">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>|  
|[<span data-ttu-id="67c63-116">GetFunctionFromIP2-Methode</span><span class="sxs-lookup"><span data-stu-id="67c63-116">GetFunctionFromIP2 Method</span></span>](icorprofilerinfo4-getfunctionfromip2-method.md)|<span data-ttu-id="67c63-117">Ordnet einen Anweisungs Zeiger für verwalteten Code der JIT-neu kompilierten Version einer angegebenen Funktion zu.</span><span class="sxs-lookup"><span data-stu-id="67c63-117">Maps a managed code instruction pointer to the JIT-recompiled version of a specified function.</span></span>|  
|[<span data-ttu-id="67c63-118">GetILToNativeMapping2-Methode</span><span class="sxs-lookup"><span data-stu-id="67c63-118">GetILToNativeMapping2 Method</span></span>](icorprofilerinfo4-getiltonativemapping2-method.md)|<span data-ttu-id="67c63-119">Ruft eine Zuordnung von MSIL-Offsets (Microsoft Intermediate Language) zu nativen Offsets für den Code ab, der in der JIT-neu kompilierten Version der angegebenen Funktion enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="67c63-119">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function .</span></span>|  
|[<span data-ttu-id="67c63-120">GetObjectSize2-Methode</span><span class="sxs-lookup"><span data-stu-id="67c63-120">GetObjectSize2 Method</span></span>](icorprofilerinfo4-getobjectsize2-method.md)|<span data-ttu-id="67c63-121">Gibt die Größe eines angegebenen-Objekts zurück.</span><span class="sxs-lookup"><span data-stu-id="67c63-121">Returns the size of a specified object.</span></span>|  
|[<span data-ttu-id="67c63-122">GetReJITIDs-Methode</span><span class="sxs-lookup"><span data-stu-id="67c63-122">GetReJITIDs Method</span></span>](icorprofilerinfo4-getrejitids-method.md)|<span data-ttu-id="67c63-123">Gibt ein Array von IDs zurück, die alle JIT-neu kompilierten Versionen der angegebenen Funktion identifizieren, die noch zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="67c63-123">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span>|  
|[<span data-ttu-id="67c63-124">InitializeCurrentThread-Methode</span><span class="sxs-lookup"><span data-stu-id="67c63-124">InitializeCurrentThread Method</span></span>](icorprofilerinfo4-initializecurrentthread-method.md)|<span data-ttu-id="67c63-125">Initialisiert den aktuellen Thread vor nachfolgenden Profiler-API-aufrufen im gleichen Thread, sodass der Deadlock vermieden werden kann.</span><span class="sxs-lookup"><span data-stu-id="67c63-125">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>|  
|[<span data-ttu-id="67c63-126">RequestReJIT-Methode</span><span class="sxs-lookup"><span data-stu-id="67c63-126">RequestReJIT Method</span></span>](icorprofilerinfo4-requestrejit-method.md)|<span data-ttu-id="67c63-127">Fordert eine JIT-Neukompilierung aller Instanzen der angegebenen Funktionen an.</span><span class="sxs-lookup"><span data-stu-id="67c63-127">Requests a JIT recompilation of all instances of the specified functions.</span></span>|  
|[<span data-ttu-id="67c63-128">RequestRevert-Methode</span><span class="sxs-lookup"><span data-stu-id="67c63-128">RequestRevert Method</span></span>](icorprofilerinfo4-requestrevert-method.md)|<span data-ttu-id="67c63-129">Setzt alle Instanzen der angegebenen Funktionen auf die ursprünglichen Versionen zurück.</span><span class="sxs-lookup"><span data-stu-id="67c63-129">Reverts all instances of the specified functions to their original versions.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67c63-130">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="67c63-130">Remarks</span></span>  
 <span data-ttu-id="67c63-131">Die CLR implementiert die Methoden der `ICorProfilerInfo4`-Schnittstelle mithilfe des Freethreadmodells.</span><span class="sxs-lookup"><span data-stu-id="67c63-131">The CLR implements the methods of the `ICorProfilerInfo4` interface by using the free-threaded model.</span></span> <span data-ttu-id="67c63-132">Jede Methode gibt ein HRESULT zurück, um einen Erfolg oder einen Fehler anzugeben.</span><span class="sxs-lookup"><span data-stu-id="67c63-132">Each method returns an HRESULT to indicate success or failure.</span></span> <span data-ttu-id="67c63-133">Eine Liste möglicher Rückgabecodes finden Sie in der Datei "CorError.h".</span><span class="sxs-lookup"><span data-stu-id="67c63-133">For a list of possible return codes, see the CorError.h file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67c63-134">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="67c63-134">Requirements</span></span>  
 <span data-ttu-id="67c63-135">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67c63-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67c63-136">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="67c63-136">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="67c63-137">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67c63-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67c63-138">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67c63-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67c63-139">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="67c63-139">See also</span></span>

- [<span data-ttu-id="67c63-140">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="67c63-140">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="67c63-141">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="67c63-141">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
