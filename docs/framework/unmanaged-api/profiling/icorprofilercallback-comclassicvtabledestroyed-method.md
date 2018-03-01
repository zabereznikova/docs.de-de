---
title: ICorProfilerCallback::COMClassicVTableDestroyed-Methode
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
- ICorProfilerCallback.COMClassicVTableDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::COMClassicVTableDestroyed
helpviewer_keywords:
- ICorProfilerCallback::COMClassicVTableDestroyed method [.NET Framework profiling]
- COMClassicVTableDestroyed method [.NET Framework profiling]
ms.assetid: 29da20ca-bf39-4356-8099-d9c3ac3423a9
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 74ee3f0ca092710342b48b8adbaa5f5cf7e8b980
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackcomclassicvtabledestroyed-method"></a><span data-ttu-id="29271-102">ICorProfilerCallback::COMClassicVTableDestroyed-Methode</span><span class="sxs-lookup"><span data-stu-id="29271-102">ICorProfilerCallback::COMClassicVTableDestroyed Method</span></span>
<span data-ttu-id="29271-103">Benachrichtigt den Profiler, dass eine COM-Interop-Vtable zerstört wird.</span><span class="sxs-lookup"><span data-stu-id="29271-103">Notifies the profiler that a COM interop vtable is being destroyed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="29271-104">Dieser Rückruf wird wahrscheinlich nie auftreten, da die Zerstörung der v-Tabellen sehr nahe Herunterfahren auftritt.</span><span class="sxs-lookup"><span data-stu-id="29271-104">This callback is likely never to occur, because the destruction of vtables occurs very close to shutdown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29271-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="29271-105">Syntax</span></span>  
  
```  
HRESULT COMClassicVTableDestroyed(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="29271-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="29271-106">Parameters</span></span>  
 `wrappedClasId`  
 <span data-ttu-id="29271-107">[in] Die ID der Klasse für die diese Vtable erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="29271-107">[in] The ID of the class for which this vtable was created.</span></span>  
  
 `implementedIID`  
 <span data-ttu-id="29271-108">[in] Die ID der Schnittstelle, die von der Klasse implementiert.</span><span class="sxs-lookup"><span data-stu-id="29271-108">[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="29271-109">Dieser Wert kann NULL sein, wenn die Schnittstelle nur intern verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="29271-109">This value may be NULL if the interface is internal only.</span></span>  
  
 `pVTable`  
 <span data-ttu-id="29271-110">[in] Ein Zeiger auf den Anfang des Vtable.</span><span class="sxs-lookup"><span data-stu-id="29271-110">[in] A pointer to the start of the vtable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29271-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="29271-111">Remarks</span></span>  
 <span data-ttu-id="29271-112">Der Profiler sollte in ihrer Implementierung dieser Methode nicht blockieren, da der Stapel nicht in einem Zustand ist, die Garbagecollection zulässt, und deshalb Präemptive Garbagecollection nicht aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="29271-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="29271-113">Wenn der Profiler hier blockiert und Garbagecollection wird versucht, die Laufzeit blockiert, bis dieser Rückruf zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="29271-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="29271-114">Der Profiler Implementierung dieser Methode sollten nicht in verwaltetem Code oder in einer verwalteten Speicher reservieren aufrufen.</span><span class="sxs-lookup"><span data-stu-id="29271-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29271-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="29271-115">Requirements</span></span>  
 <span data-ttu-id="29271-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29271-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29271-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="29271-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="29271-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29271-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29271-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29271-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29271-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29271-120">See Also</span></span>  
 [<span data-ttu-id="29271-121">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29271-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="29271-122">COMClassicVTableCreated-Methode</span><span class="sxs-lookup"><span data-stu-id="29271-122">COMClassicVTableCreated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtablecreated-method.md)
