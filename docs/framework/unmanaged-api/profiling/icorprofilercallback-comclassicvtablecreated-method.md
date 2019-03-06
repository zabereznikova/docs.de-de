---
title: ICorProfilerCallback::COMClassicVTableCreated-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 86d0ff4f9dd2957213974b2723734e49729256a7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466478"
---
# <a name="icorprofilercallbackcomclassicvtablecreated-method"></a><span data-ttu-id="c5dbd-102">ICorProfilerCallback::COMClassicVTableCreated-Methode</span><span class="sxs-lookup"><span data-stu-id="c5dbd-102">ICorProfilerCallback::COMClassicVTableCreated Method</span></span>
<span data-ttu-id="c5dbd-103">Benachrichtigt den Profiler an, eine COM-Interop-Vtable für die angegebene IID und Klasse erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c5dbd-103">Notifies the profiler that a COM interop vtable for the specified IID and class has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5dbd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c5dbd-104">Syntax</span></span>  
  
```  
HRESULT COMClassicVTableCreated(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable,  
    [in] ULONG   cSlots);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5dbd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c5dbd-105">Parameters</span></span>  
 `wrappedClasId`  
 <span data-ttu-id="c5dbd-106">[in] Die ID der Klasse für die die Vtable erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c5dbd-106">[in] The ID of the class for which the vtable has been created.</span></span>  
  
 `implementedIID`  
 <span data-ttu-id="c5dbd-107">[in] Die ID der von der Klasse implementierten Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c5dbd-107">[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="c5dbd-108">Dieser Wert kann NULL sein, wenn die Schnittstelle ausschließlich intern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c5dbd-108">This value may be NULL if the interface is internal only.</span></span>  
  
 `pVTable`  
 <span data-ttu-id="c5dbd-109">[in] Ein Zeiger auf den Anfang der Vtable.</span><span class="sxs-lookup"><span data-stu-id="c5dbd-109">[in] A pointer to the start of the vtable.</span></span>  
  
 `cSlots`  
 <span data-ttu-id="c5dbd-110">[in] Die Anzahl der Steckplätze, die in der Vtable sind.</span><span class="sxs-lookup"><span data-stu-id="c5dbd-110">[in] The number of slots that are in the vtable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5dbd-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c5dbd-111">Remarks</span></span>  
 <span data-ttu-id="c5dbd-112">Der Profiler sollte die Implementierung dieser Methode nicht blockieren, da der Stapel nicht in einem Zustand handeln, der Garbagecollection zulässt, und daher die Präemptive Garbagecollection kann nicht aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="c5dbd-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="c5dbd-113">Wenn der Profiler hier blockiert und Garbagecollection wird versucht, die Laufzeit blockiert, bis dieser Rückruf zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c5dbd-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="c5dbd-114">Der Profiler Implementierung dieser Methode sollte nicht in verwaltetem Code oder in einer verwalteten Speicher reservieren aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c5dbd-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5dbd-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c5dbd-115">Requirements</span></span>  
 <span data-ttu-id="c5dbd-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5dbd-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5dbd-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c5dbd-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c5dbd-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5dbd-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5dbd-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5dbd-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5dbd-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5dbd-120">See also</span></span>
- [<span data-ttu-id="c5dbd-121">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c5dbd-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="c5dbd-122">COMClassicVTableDestroyed-Methode</span><span class="sxs-lookup"><span data-stu-id="c5dbd-122">COMClassicVTableDestroyed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtabledestroyed-method.md)
