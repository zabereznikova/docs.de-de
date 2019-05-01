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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 177e5ef8054f408dc8ec3475c56043394a636bc0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049452"
---
# <a name="icorprofilerinfo4-interface"></a><span data-ttu-id="621bb-102">ICorProfilerInfo4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="621bb-102">ICorProfilerInfo4 Interface</span></span>
<span data-ttu-id="621bb-103">Enthält Methoden, mit denen Codeprofiler mit der common Language Runtime (CLR), um die ereignisüberwachung zu steuern und Informationen zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="621bb-103">Provides methods that code profilers use to communicate with the common language runtime (CLR) to control event monitoring and request information.</span></span> <span data-ttu-id="621bb-104">sein.</span><span class="sxs-lookup"><span data-stu-id="621bb-104">.</span></span> <span data-ttu-id="621bb-105">Die `ICorProfilerInfo4` Schnittstelle ist eine Erweiterung der anderen `ICorProfilerInfo` Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="621bb-105">The `ICorProfilerInfo4` interface is an extension of the other `ICorProfilerInfo` interfaces.</span></span> <span data-ttu-id="621bb-106">Es bietet neue Methoden zur Unterstützung der just-in-Time (JIT) Neukompilierung hinzugefügt, die der [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="621bb-106">It provides new methods to support just-in-time (JIT) recompilation, added in the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span></span>  
  
## <a name="methods"></a><span data-ttu-id="621bb-107">Methoden</span><span class="sxs-lookup"><span data-stu-id="621bb-107">Methods</span></span>  
  
|<span data-ttu-id="621bb-108">Methode</span><span class="sxs-lookup"><span data-stu-id="621bb-108">Method</span></span>|<span data-ttu-id="621bb-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="621bb-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="621bb-110">EnumJITedFunctions2-Methode</span><span class="sxs-lookup"><span data-stu-id="621bb-110">EnumJITedFunctions2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)|<span data-ttu-id="621bb-111">Gibt einen Enumerator für alle Funktionen, die JIT-kompiliert und erneut JIT-kompilierten zuvor waren.</span><span class="sxs-lookup"><span data-stu-id="621bb-111">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span>|  
|[<span data-ttu-id="621bb-112">EnumThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="621bb-112">EnumThreads Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumthreads-method.md)|<span data-ttu-id="621bb-113">Ruft einen Enumerator, der Methoden, um Sie sequenziell zu durchlaufen, bis die Auflistung aller verwalteten Threads im profilierten Prozess bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="621bb-113">Gets an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>|  
|[<span data-ttu-id="621bb-114">GetCodeInfo3-Methode</span><span class="sxs-lookup"><span data-stu-id="621bb-114">GetCodeInfo3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md)|<span data-ttu-id="621bb-115">Ruft die Erweiterungen des systemeigenen Codes ab, die der JIT-kompilierten Version der angegebenen Funktion zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="621bb-115">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>|  
|[<span data-ttu-id="621bb-116">GetFunctionFromIP2-Methode</span><span class="sxs-lookup"><span data-stu-id="621bb-116">GetFunctionFromIP2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getfunctionfromip2-method.md)|<span data-ttu-id="621bb-117">Ordnet einen Anweisungszeiger im verwalteten Code die JIT-kompilierten Version einer angegebenen Funktion.</span><span class="sxs-lookup"><span data-stu-id="621bb-117">Maps a managed code instruction pointer to the JIT-recompiled version of a specified function.</span></span>|  
|[<span data-ttu-id="621bb-118">GetILToNativeMapping2-Methode</span><span class="sxs-lookup"><span data-stu-id="621bb-118">GetILToNativeMapping2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getiltonativemapping2-method.md)|<span data-ttu-id="621bb-119">Ruft eine Zuordnung von Microsoft intermediate Language (MSIL)-und systemeigenen Offsets für den in der erneut JIT-kompilierten Version der angegebenen Funktion enthaltenen Code Offsets ab.</span><span class="sxs-lookup"><span data-stu-id="621bb-119">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function .</span></span>|  
|[<span data-ttu-id="621bb-120">GetObjectSize2-Methode</span><span class="sxs-lookup"><span data-stu-id="621bb-120">GetObjectSize2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md)|<span data-ttu-id="621bb-121">Gibt die Größe eines angegebenen Objekts zurück.</span><span class="sxs-lookup"><span data-stu-id="621bb-121">Returns the size of a specified object.</span></span>|  
|[<span data-ttu-id="621bb-122">GetReJITIDs-Methode</span><span class="sxs-lookup"><span data-stu-id="621bb-122">GetReJITIDs Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getrejitids-method.md)|<span data-ttu-id="621bb-123">Gibt ein Array von IDs, die alle erneut JIT-kompilierte Versionen der angegebenen Funktion zu identifizieren, die immer noch zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="621bb-123">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span>|  
|[<span data-ttu-id="621bb-124">InitializeCurrentThread-Methode</span><span class="sxs-lookup"><span data-stu-id="621bb-124">InitializeCurrentThread Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-initializecurrentthread-method.md)|<span data-ttu-id="621bb-125">Initialisiert den aktuellen Thread im Voraus über nachfolgende Profiler, die auf dem gleichen Thread, API-Aufrufe, sodass dieser Deadlock vermieden werden kann.</span><span class="sxs-lookup"><span data-stu-id="621bb-125">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>|  
|[<span data-ttu-id="621bb-126">RequestReJIT-Methode</span><span class="sxs-lookup"><span data-stu-id="621bb-126">RequestReJIT Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md)|<span data-ttu-id="621bb-127">Fordert eine JIT-Neukompilierung aller Instanzen der angegebenen Funktionen an.</span><span class="sxs-lookup"><span data-stu-id="621bb-127">Requests a JIT recompilation of all instances of the specified functions.</span></span>|  
|[<span data-ttu-id="621bb-128">RequestRevert-Methode</span><span class="sxs-lookup"><span data-stu-id="621bb-128">RequestRevert Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md)|<span data-ttu-id="621bb-129">Setzt alle Instanzen der angegebenen Funktionen auf die ursprünglichen Versionen zurück.</span><span class="sxs-lookup"><span data-stu-id="621bb-129">Reverts all instances of the specified functions to their original versions.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="621bb-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="621bb-130">Remarks</span></span>  
 <span data-ttu-id="621bb-131">Die CLR implementiert die Methoden der `ICorProfilerInfo4`-Schnittstelle mithilfe des Freethreadmodells.</span><span class="sxs-lookup"><span data-stu-id="621bb-131">The CLR implements the methods of the `ICorProfilerInfo4` interface by using the free-threaded model.</span></span> <span data-ttu-id="621bb-132">Jede Methode gibt ein HRESULT zurück, um einen Erfolg oder einen Fehler anzugeben.</span><span class="sxs-lookup"><span data-stu-id="621bb-132">Each method returns an HRESULT to indicate success or failure.</span></span> <span data-ttu-id="621bb-133">Eine Liste möglicher Rückgabecodes finden Sie in der Datei "CorError.h".</span><span class="sxs-lookup"><span data-stu-id="621bb-133">For a list of possible return codes, see the CorError.h file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="621bb-134">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="621bb-134">Requirements</span></span>  
 <span data-ttu-id="621bb-135">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="621bb-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="621bb-136">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="621bb-136">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="621bb-137">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="621bb-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="621bb-138">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="621bb-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="621bb-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="621bb-139">See also</span></span>

- [<span data-ttu-id="621bb-140">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="621bb-140">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="621bb-141">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="621bb-141">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
