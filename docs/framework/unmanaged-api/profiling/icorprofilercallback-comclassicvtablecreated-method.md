---
title: ICorProfilerCallback::COMClassicVTableCreated-Methode
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
- ICorProfilerCallback.COMClassicVTableCreated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::COMClassicVTableCreated
helpviewer_keywords:
- COMClassicVTableCreated method [.NET Framework profiling]
- ICorProfilerCallback::COMClassicVTableCreated method [.NET Framework profiling]
ms.assetid: 6e1834ab-c359-498a-b10b-984ae23cdda4
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 43fb447393e1d34ca53fbb62ecdc456a97452bc4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackcomclassicvtablecreated-method"></a><span data-ttu-id="b94db-102">ICorProfilerCallback::COMClassicVTableCreated-Methode</span><span class="sxs-lookup"><span data-stu-id="b94db-102">ICorProfilerCallback::COMClassicVTableCreated Method</span></span>
<span data-ttu-id="b94db-103">Benachrichtigt den Profiler, dass eine COM-Interop-Vtable für die angegebene IID und Klasse erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b94db-103">Notifies the profiler that a COM interop vtable for the specified IID and class has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b94db-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b94db-104">Syntax</span></span>  
  
```  
HRESULT COMClassicVTableCreated(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable,  
    [in] ULONG   cSlots);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b94db-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b94db-105">Parameters</span></span>  
 `wrappedClasId`  
 <span data-ttu-id="b94db-106">[in] Die ID der Klasse für die Vtable erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b94db-106">[in] The ID of the class for which the vtable has been created.</span></span>  
  
 `implementedIID`  
 <span data-ttu-id="b94db-107">[in] Die ID der Schnittstelle, die von der Klasse implementiert.</span><span class="sxs-lookup"><span data-stu-id="b94db-107">[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="b94db-108">Dieser Wert kann NULL sein, wenn die Schnittstelle nur intern verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="b94db-108">This value may be NULL if the interface is internal only.</span></span>  
  
 `pVTable`  
 <span data-ttu-id="b94db-109">[in] Ein Zeiger auf den Anfang des Vtable.</span><span class="sxs-lookup"><span data-stu-id="b94db-109">[in] A pointer to the start of the vtable.</span></span>  
  
 `cSlots`  
 <span data-ttu-id="b94db-110">[in] Die Anzahl der Steckplätze, die im Vtable sind.</span><span class="sxs-lookup"><span data-stu-id="b94db-110">[in] The number of slots that are in the vtable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b94db-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b94db-111">Remarks</span></span>  
 <span data-ttu-id="b94db-112">Der Profiler sollte in ihrer Implementierung dieser Methode nicht blockieren, da der Stapel nicht in einem Zustand ist, die Garbagecollection zulässt, und deshalb Präemptive Garbagecollection nicht aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b94db-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="b94db-113">Wenn der Profiler hier blockiert und Garbagecollection wird versucht, die Laufzeit blockiert, bis dieser Rückruf zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b94db-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="b94db-114">Der Profiler Implementierung dieser Methode sollten nicht in verwaltetem Code oder in einer verwalteten Speicher reservieren aufrufen.</span><span class="sxs-lookup"><span data-stu-id="b94db-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b94db-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b94db-115">Requirements</span></span>  
 <span data-ttu-id="b94db-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b94db-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b94db-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b94db-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b94db-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b94db-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b94db-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b94db-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b94db-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b94db-120">See Also</span></span>  
 [<span data-ttu-id="b94db-121">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b94db-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="b94db-122">COMClassicVTableDestroyed-Methode</span><span class="sxs-lookup"><span data-stu-id="b94db-122">COMClassicVTableDestroyed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtabledestroyed-method.md)
