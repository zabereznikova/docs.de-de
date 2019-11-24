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
ms.openlocfilehash: cbd7c0d8fff55766a98e727ce22c77dd5214611b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448003"
---
# <a name="icorprofilerinfo4-interface"></a><span data-ttu-id="5ea04-102">ICorProfilerInfo4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5ea04-102">ICorProfilerInfo4 Interface</span></span>
<span data-ttu-id="5ea04-103">Provides methods that code profilers use to communicate with the common language runtime (CLR) to control event monitoring and request information.</span><span class="sxs-lookup"><span data-stu-id="5ea04-103">Provides methods that code profilers use to communicate with the common language runtime (CLR) to control event monitoring and request information.</span></span> <span data-ttu-id="5ea04-104">sein.</span><span class="sxs-lookup"><span data-stu-id="5ea04-104">.</span></span> <span data-ttu-id="5ea04-105">The `ICorProfilerInfo4` interface is an extension of the other `ICorProfilerInfo` interfaces.</span><span class="sxs-lookup"><span data-stu-id="5ea04-105">The `ICorProfilerInfo4` interface is an extension of the other `ICorProfilerInfo` interfaces.</span></span> <span data-ttu-id="5ea04-106">It provides new methods to support just-in-time (JIT) recompilation, added in the .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="5ea04-106">It provides new methods to support just-in-time (JIT) recompilation, added in the .NET Framework 4.5.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5ea04-107">Methoden</span><span class="sxs-lookup"><span data-stu-id="5ea04-107">Methods</span></span>  
  
|<span data-ttu-id="5ea04-108">Methode</span><span class="sxs-lookup"><span data-stu-id="5ea04-108">Method</span></span>|<span data-ttu-id="5ea04-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5ea04-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5ea04-110">EnumJITedFunctions2-Methode</span><span class="sxs-lookup"><span data-stu-id="5ea04-110">EnumJITedFunctions2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)|<span data-ttu-id="5ea04-111">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span><span class="sxs-lookup"><span data-stu-id="5ea04-111">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span>|  
|[<span data-ttu-id="5ea04-112">EnumThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="5ea04-112">EnumThreads Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumthreads-method.md)|<span data-ttu-id="5ea04-113">Gets an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span><span class="sxs-lookup"><span data-stu-id="5ea04-113">Gets an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>|  
|[<span data-ttu-id="5ea04-114">GetCodeInfo3-Methode</span><span class="sxs-lookup"><span data-stu-id="5ea04-114">GetCodeInfo3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md)|<span data-ttu-id="5ea04-115">Ruft die Erweiterungen des systemeigenen Codes ab, die der JIT-kompilierten Version der angegebenen Funktion zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="5ea04-115">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>|  
|[<span data-ttu-id="5ea04-116">GetFunctionFromIP2-Methode</span><span class="sxs-lookup"><span data-stu-id="5ea04-116">GetFunctionFromIP2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getfunctionfromip2-method.md)|<span data-ttu-id="5ea04-117">Maps a managed code instruction pointer to the JIT-recompiled version of a specified function.</span><span class="sxs-lookup"><span data-stu-id="5ea04-117">Maps a managed code instruction pointer to the JIT-recompiled version of a specified function.</span></span>|  
|[<span data-ttu-id="5ea04-118">GetILToNativeMapping2-Methode</span><span class="sxs-lookup"><span data-stu-id="5ea04-118">GetILToNativeMapping2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getiltonativemapping2-method.md)|<span data-ttu-id="5ea04-119">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function .</span><span class="sxs-lookup"><span data-stu-id="5ea04-119">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the JIT-recompiled version of the specified function .</span></span>|  
|[<span data-ttu-id="5ea04-120">GetObjectSize2-Methode</span><span class="sxs-lookup"><span data-stu-id="5ea04-120">GetObjectSize2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md)|<span data-ttu-id="5ea04-121">Returns the size of a specified object.</span><span class="sxs-lookup"><span data-stu-id="5ea04-121">Returns the size of a specified object.</span></span>|  
|[<span data-ttu-id="5ea04-122">GetReJITIDs-Methode</span><span class="sxs-lookup"><span data-stu-id="5ea04-122">GetReJITIDs Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getrejitids-method.md)|<span data-ttu-id="5ea04-123">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span><span class="sxs-lookup"><span data-stu-id="5ea04-123">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span>|  
|[<span data-ttu-id="5ea04-124">InitializeCurrentThread-Methode</span><span class="sxs-lookup"><span data-stu-id="5ea04-124">InitializeCurrentThread Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-initializecurrentthread-method.md)|<span data-ttu-id="5ea04-125">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span><span class="sxs-lookup"><span data-stu-id="5ea04-125">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>|  
|[<span data-ttu-id="5ea04-126">RequestReJIT-Methode</span><span class="sxs-lookup"><span data-stu-id="5ea04-126">RequestReJIT Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md)|<span data-ttu-id="5ea04-127">Fordert eine JIT-Neukompilierung aller Instanzen der angegebenen Funktionen an.</span><span class="sxs-lookup"><span data-stu-id="5ea04-127">Requests a JIT recompilation of all instances of the specified functions.</span></span>|  
|[<span data-ttu-id="5ea04-128">RequestRevert-Methode</span><span class="sxs-lookup"><span data-stu-id="5ea04-128">RequestRevert Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md)|<span data-ttu-id="5ea04-129">Setzt alle Instanzen der angegebenen Funktionen auf die ursprünglichen Versionen zurück.</span><span class="sxs-lookup"><span data-stu-id="5ea04-129">Reverts all instances of the specified functions to their original versions.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ea04-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5ea04-130">Remarks</span></span>  
 <span data-ttu-id="5ea04-131">Die CLR implementiert die Methoden der `ICorProfilerInfo4`-Schnittstelle mithilfe des Freethreadmodells.</span><span class="sxs-lookup"><span data-stu-id="5ea04-131">The CLR implements the methods of the `ICorProfilerInfo4` interface by using the free-threaded model.</span></span> <span data-ttu-id="5ea04-132">Jede Methode gibt ein HRESULT zurück, um einen Erfolg oder einen Fehler anzugeben.</span><span class="sxs-lookup"><span data-stu-id="5ea04-132">Each method returns an HRESULT to indicate success or failure.</span></span> <span data-ttu-id="5ea04-133">Eine Liste möglicher Rückgabecodes finden Sie in der Datei "CorError.h".</span><span class="sxs-lookup"><span data-stu-id="5ea04-133">For a list of possible return codes, see the CorError.h file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ea04-134">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5ea04-134">Requirements</span></span>  
 <span data-ttu-id="5ea04-135">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ea04-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ea04-136">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5ea04-136">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5ea04-137">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ea04-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ea04-138">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ea04-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ea04-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ea04-139">See also</span></span>

- [<span data-ttu-id="5ea04-140">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="5ea04-140">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="5ea04-141">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5ea04-141">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
