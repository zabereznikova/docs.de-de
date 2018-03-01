---
title: ICorProfilerCallback4::ReJITError-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback4.ReJITError
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITError
helpviewer_keywords:
- ReJITError method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITError method [.NET Framework profiling]
ms.assetid: d7888aa9-dfaa-420f-9f99-e06ab35ca482
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c746d0f7a6be96f95f1a051e22de0ad1bd2d2269
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback4rejiterror-method"></a><span data-ttu-id="80f8f-102">ICorProfilerCallback4::ReJITError-Methode</span><span class="sxs-lookup"><span data-stu-id="80f8f-102">ICorProfilerCallback4::ReJITError Method</span></span>
<span data-ttu-id="80f8f-103">Benachrichtigt den Profiler, dass der Just-in-Time (JIT)-Compiler einen Fehler bei der Neukompilierung aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="80f8f-103">Notifies the profiler that the just-in-time (JIT) compiler encountered an error in the recompilation process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80f8f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="80f8f-104">Syntax</span></span>  
  
```  
HRESULT ReJITError(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodId,  
    [in] FunctionID  functionId,  
    [in] HRESULT     hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="80f8f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="80f8f-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="80f8f-106">[in] Die `ModuleID` in dem die fehlerhaften Neukompilierung versucht wurde.</span><span class="sxs-lookup"><span data-stu-id="80f8f-106">[in] The `ModuleID` in which the failed recompilation attempt was made.</span></span>  
  
 `methodId`  
 <span data-ttu-id="80f8f-107">[in] Die `MethodDef` der Methode, die auf dem die fehlerhaften Neukompilierung versucht wurde.</span><span class="sxs-lookup"><span data-stu-id="80f8f-107">[in] The `MethodDef` of the method on which the failed recompilation attempt was made.</span></span>  
  
 `functionId`  
 <span data-ttu-id="80f8f-108">[in] Die Funktionsinstanz, die erneut kompilierte oder für das neu kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="80f8f-108">[in] The function instance that is being recompiled or marked for recompilation.</span></span> <span data-ttu-id="80f8f-109">Dieser Wert möglicherweise `NULL` Wenn regelmäßig jede Methode anstelle einer pro-Instanziierung-Basis (beispielsweise, wenn der Profiler eine ungültige Metadatentoken für die Methode für die erneute Kompilierung angegeben), der der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="80f8f-109">This value may be `NULL` if the failure occurred on a per-method basis instead of a per-instantiation basis (for example, if the profiler specified an invalid metadata token for the method to be recompiled).</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="80f8f-110">[in] Ein HRESULT, das die Art des Fehlers angibt.</span><span class="sxs-lookup"><span data-stu-id="80f8f-110">[in] An HRESULT that indicates the nature of the failure.</span></span> <span data-ttu-id="80f8f-111">Finden Sie im Abschnitt "Status HRESULTS" eine Liste von Werten aus.</span><span class="sxs-lookup"><span data-stu-id="80f8f-111">See the Status HRESULTS section for a list of values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80f8f-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="80f8f-112">Return Value</span></span>  
 <span data-ttu-id="80f8f-113">Rückgabewerte von diesem Rückruf werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="80f8f-113">Return values from this callback are ignored.</span></span>  
  
## <a name="status-hresults"></a><span data-ttu-id="80f8f-114">Status HRESULTS</span><span class="sxs-lookup"><span data-stu-id="80f8f-114">Status HRESULTS</span></span>  
  
|<span data-ttu-id="80f8f-115">Statusarray HRESULT</span><span class="sxs-lookup"><span data-stu-id="80f8f-115">Status array HRESULT</span></span>|<span data-ttu-id="80f8f-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="80f8f-116">Description</span></span>|  
|--------------------------|-----------------|  
|<span data-ttu-id="80f8f-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="80f8f-117">E_INVALIDARG</span></span>|<span data-ttu-id="80f8f-118">Die `moduleID` oder `methodDef` Token ist `NULL`.</span><span class="sxs-lookup"><span data-stu-id="80f8f-118">The `moduleID` or `methodDef` token is `NULL`.</span></span>|  
|<span data-ttu-id="80f8f-119">CORPROF_E_DATAINCOMPLETE</span><span class="sxs-lookup"><span data-stu-id="80f8f-119">CORPROF_E_DATAINCOMPLETE</span></span>|<span data-ttu-id="80f8f-120">Das Modul ist noch nicht vollständig geladen, oder es wird gerade entladen.</span><span class="sxs-lookup"><span data-stu-id="80f8f-120">The module is not fully loaded yet, or it is in the process of being unloaded.</span></span>|  
|<span data-ttu-id="80f8f-121">CORPROF_E_MODULE_IS_DYNAMIC</span><span class="sxs-lookup"><span data-stu-id="80f8f-121">CORPROF_E_MODULE_IS_DYNAMIC</span></span>|<span data-ttu-id="80f8f-122">Das angegebene Modul wurde dynamisch generiert (z. B. durch `Reflection.Emit`), und wird daher von dieser Methode nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="80f8f-122">The specified module was dynamically generated (for example, by `Reflection.Emit`), and is thus not supported by this method.</span></span>|  
|<span data-ttu-id="80f8f-123">CORPROF_E_FUNCTION_IS_COLLECTIBLE</span><span class="sxs-lookup"><span data-stu-id="80f8f-123">CORPROF_E_FUNCTION_IS_COLLECTIBLE</span></span>|<span data-ttu-id="80f8f-124">Die Methode in einer entladbare Assembly instanziiert wird, und kann daher nicht neu kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="80f8f-124">The method is instantiated into a collectible assembly, and is therefore not able to be recompiled.</span></span> <span data-ttu-id="80f8f-125">Beachten Sie, die von Typen und Funktionen, die in einen Reflektionskontext definiert (z. B. `List<MyCollectibleStruct>`) in einer entladbare Assembly instanziiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="80f8f-125">Note that types and functions defined in a non-reflection context (for example, `List<MyCollectibleStruct>`) can be instantiated into a collectible assembly.</span></span>|  
|<span data-ttu-id="80f8f-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="80f8f-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="80f8f-127">Die CLR den Puffertypen nicht genügend Arbeitsspeicher auf die angegebene Methode für die JIT-Neukompilierung zu markieren.</span><span class="sxs-lookup"><span data-stu-id="80f8f-127">The CLR ran out of memory while trying to mark the specified method for JIT recompilation.</span></span>|  
|<span data-ttu-id="80f8f-128">Andere</span><span class="sxs-lookup"><span data-stu-id="80f8f-128">Other</span></span>|<span data-ttu-id="80f8f-129">Das Betriebssystem hat einen Fehler außerhalb der Kontrolle der CLR zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="80f8f-129">The operating system returned a failure outside the control of the CLR.</span></span> <span data-ttu-id="80f8f-130">Beispielsweise wird ein Systemaufruf zum Ändern des Zugriffsschutz einer Seite des Speichers ein Fehler auftritt, der Betriebssystemfehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="80f8f-130">For example, if a system call to change the access protection of a page of memory fails, the operating system error is displayed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="80f8f-131">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="80f8f-131">Requirements</span></span>  
 <span data-ttu-id="80f8f-132">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80f8f-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80f8f-133">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="80f8f-133">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="80f8f-134">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80f8f-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80f8f-135">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80f8f-135">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80f8f-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80f8f-136">See Also</span></span>  
 [<span data-ttu-id="80f8f-137">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="80f8f-137">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="80f8f-138">ICorProfilerCallback4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="80f8f-138">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
