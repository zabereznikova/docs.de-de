---
title: ICorProfilerInfo4-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo4
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo4
helpviewer_keywords: ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 80a5308e-c22f-4201-ba89-31cc8562515b
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: db91347ad2c951c28ea7b653336450929d37bdcb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo4-interface"></a><span data-ttu-id="a015c-102">ICorProfilerInfo4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a015c-102">ICorProfilerInfo4 Interface</span></span>
<span data-ttu-id="a015c-103">Enthält Methoden, mit denen Codeprofiler mit der common Language Runtime (CLR), um die ereignisüberwachung zu steuern und Informationen zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="a015c-103">Provides methods that code profilers use to communicate with the common language runtime (CLR) to control event monitoring and request information.</span></span> <span data-ttu-id="a015c-104">.</span><span class="sxs-lookup"><span data-stu-id="a015c-104">.</span></span> <span data-ttu-id="a015c-105">Die `ICorProfilerInfo4` Schnittstelle ist eine Erweiterung der anderen `ICorProfilerInfo` Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="a015c-105">The `ICorProfilerInfo4` interface is an extension of the other `ICorProfilerInfo` interfaces.</span></span> <span data-ttu-id="a015c-106">Es bietet neue Methoden zur Unterstützung von Just-in-Time (JIT)-Neukompilierung hinzugefügt, der [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a015c-106">It provides new methods to support just-in-time (JIT) recompilation, added in the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a015c-107">Methoden</span><span class="sxs-lookup"><span data-stu-id="a015c-107">Methods</span></span>  
  
|<span data-ttu-id="a015c-108">Methode</span><span class="sxs-lookup"><span data-stu-id="a015c-108">Method</span></span>|<span data-ttu-id="a015c-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a015c-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a015c-110">EnumJITedFunctions2-Methode</span><span class="sxs-lookup"><span data-stu-id="a015c-110">EnumJITedFunctions2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)|<span data-ttu-id="a015c-111">Gibt einen Enumerator für alle Funktionen, die bereits JIT-kompiliert und JIT-kompiliert wurden.</span><span class="sxs-lookup"><span data-stu-id="a015c-111">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span>|  
|[<span data-ttu-id="a015c-112">EnumThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="a015c-112">EnumThreads Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumthreads-method.md)|<span data-ttu-id="a015c-113">Ruft einem Enumerator ab, das Methoden zum sequenziellen iterieren durch die Auflistung aller verwalteten Threads im profilierten Prozess bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="a015c-113">Gets an enumerator that that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>|  
|[<span data-ttu-id="a015c-114">GetCodeInfo3-Methode</span><span class="sxs-lookup"><span data-stu-id="a015c-114">GetCodeInfo3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md)|<span data-ttu-id="a015c-115">Ruft die Erweiterungen des nativen Codes ab, die der JIT-kompilierten Version der angegebenen Funktion zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="a015c-115">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>|  
|[<span data-ttu-id="a015c-116">GetFunctionFromIP2-Methode</span><span class="sxs-lookup"><span data-stu-id="a015c-116">GetFunctionFromIP2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getfunctionfromip2-method.md)|<span data-ttu-id="a015c-117">Ordnet einen verwalteten Code Anweisungszeiger der JIT-kompilierten Version einer angegebenen Funktion.</span><span class="sxs-lookup"><span data-stu-id="a015c-117">Maps a managed code instruction pointer to the JIT-recompiled version of a specified function.</span></span>|  
|[<span data-ttu-id="a015c-118">GetILToNativeMapping2-Methode</span><span class="sxs-lookup"><span data-stu-id="a015c-118">GetILToNativeMapping2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getiltonativemapping2-method.md)|<span data-ttu-id="a015c-119">Ruft eine Zuordnung von Microsoft intermediate Language (MSIL)-und systemeigenen Offsets für den in der JIT-kompilierten Version der angegebenen Funktion enthaltenen Code Offsets ab.</span><span class="sxs-lookup"><span data-stu-id="a015c-119">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function .</span></span>|  
|[<span data-ttu-id="a015c-120">GetObjectSize2-Methode</span><span class="sxs-lookup"><span data-stu-id="a015c-120">GetObjectSize2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md)|<span data-ttu-id="a015c-121">Gibt die Größe eines angegebenen Objekts zurück.</span><span class="sxs-lookup"><span data-stu-id="a015c-121">Returns the size of a specified object.</span></span>|  
|[<span data-ttu-id="a015c-122">GetReJITIDs-Methode</span><span class="sxs-lookup"><span data-stu-id="a015c-122">GetReJITIDs Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getrejitids-method.md)|<span data-ttu-id="a015c-123">Gibt ein Array von IDs, die alle JIT-kompilierten Version der angegebenen Funktion zu identifizieren, die dennoch zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="a015c-123">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span>|  
|[<span data-ttu-id="a015c-124">InitializeCurrentThread-Methode</span><span class="sxs-lookup"><span data-stu-id="a015c-124">InitializeCurrentThread Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-initializecurrentthread-method.md)|<span data-ttu-id="a015c-125">Initialisiert den aktuellen Thread im Vorfeld nachfolgende Profiler, die auf dem gleichen Thread-API-Aufrufe, sodass dieser Deadlock vermieden werden kann.</span><span class="sxs-lookup"><span data-stu-id="a015c-125">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>|  
|[<span data-ttu-id="a015c-126">RequestReJIT-Methode</span><span class="sxs-lookup"><span data-stu-id="a015c-126">RequestReJIT Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md)|<span data-ttu-id="a015c-127">Fordert eine JIT-Neukompilierung aller Instanzen der angegebenen Funktionen an.</span><span class="sxs-lookup"><span data-stu-id="a015c-127">Requests a JIT recompilation of all instances of the specified functions.</span></span>|  
|[<span data-ttu-id="a015c-128">RequestRevert-Methode</span><span class="sxs-lookup"><span data-stu-id="a015c-128">RequestRevert Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md)|<span data-ttu-id="a015c-129">Setzt alle Instanzen der angegebenen Funktionen auf die ursprünglichen Versionen zurück.</span><span class="sxs-lookup"><span data-stu-id="a015c-129">Reverts all instances of the specified functions to their original versions.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a015c-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a015c-130">Remarks</span></span>  
 <span data-ttu-id="a015c-131">Die CLR implementiert die Methoden der `ICorProfilerInfo4`-Schnittstelle mithilfe des Freethreadmodells.</span><span class="sxs-lookup"><span data-stu-id="a015c-131">The CLR implements the methods of the `ICorProfilerInfo4` interface by using the free-threaded model.</span></span> <span data-ttu-id="a015c-132">Jede Methode gibt ein HRESULT zurück, um einen Erfolg oder einen Fehler anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a015c-132">Each method returns an HRESULT to indicate success or failure.</span></span> <span data-ttu-id="a015c-133">Eine Liste möglicher Rückgabecodes finden Sie in der Datei "CorError.h".</span><span class="sxs-lookup"><span data-stu-id="a015c-133">For a list of possible return codes, see the CorError.h file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a015c-134">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a015c-134">Requirements</span></span>  
 <span data-ttu-id="a015c-135">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a015c-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a015c-136">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a015c-136">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a015c-137">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a015c-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a015c-138">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a015c-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a015c-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a015c-139">See Also</span></span>  
 [<span data-ttu-id="a015c-140">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="a015c-140">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="a015c-141">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a015c-141">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
