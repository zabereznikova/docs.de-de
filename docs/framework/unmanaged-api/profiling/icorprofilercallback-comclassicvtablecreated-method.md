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
ms.openlocfilehash: 79be2572f52ec509d9551261074204bf62ad5388
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445058"
---
# <a name="icorprofilercallbackcomclassicvtablecreated-method"></a><span data-ttu-id="7eff9-102">ICorProfilerCallback::COMClassicVTableCreated-Methode</span><span class="sxs-lookup"><span data-stu-id="7eff9-102">ICorProfilerCallback::COMClassicVTableCreated Method</span></span>
<span data-ttu-id="7eff9-103">Notifies the profiler that a COM interop vtable for the specified IID and class has been created.</span><span class="sxs-lookup"><span data-stu-id="7eff9-103">Notifies the profiler that a COM interop vtable for the specified IID and class has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7eff9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7eff9-104">Syntax</span></span>  
  
```cpp  
HRESULT COMClassicVTableCreated(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable,  
    [in] ULONG   cSlots);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7eff9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7eff9-105">Parameters</span></span>  
 `wrappedClasId`  
 <span data-ttu-id="7eff9-106">[in] The ID of the class for which the vtable has been created.</span><span class="sxs-lookup"><span data-stu-id="7eff9-106">[in] The ID of the class for which the vtable has been created.</span></span>  
  
 `implementedIID`  
 <span data-ttu-id="7eff9-107">[in] The ID of the interface implemented by the class.</span><span class="sxs-lookup"><span data-stu-id="7eff9-107">[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="7eff9-108">This value may be NULL if the interface is internal only.</span><span class="sxs-lookup"><span data-stu-id="7eff9-108">This value may be NULL if the interface is internal only.</span></span>  
  
 `pVTable`  
 <span data-ttu-id="7eff9-109">[in] A pointer to the start of the vtable.</span><span class="sxs-lookup"><span data-stu-id="7eff9-109">[in] A pointer to the start of the vtable.</span></span>  
  
 `cSlots`  
 <span data-ttu-id="7eff9-110">[in] The number of slots that are in the vtable.</span><span class="sxs-lookup"><span data-stu-id="7eff9-110">[in] The number of slots that are in the vtable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7eff9-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7eff9-111">Remarks</span></span>  
 <span data-ttu-id="7eff9-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span><span class="sxs-lookup"><span data-stu-id="7eff9-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="7eff9-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span><span class="sxs-lookup"><span data-stu-id="7eff9-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="7eff9-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span><span class="sxs-lookup"><span data-stu-id="7eff9-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7eff9-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7eff9-115">Requirements</span></span>  
 <span data-ttu-id="7eff9-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7eff9-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7eff9-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7eff9-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7eff9-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7eff9-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7eff9-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7eff9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eff9-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7eff9-120">See also</span></span>

- [<span data-ttu-id="7eff9-121">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7eff9-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="7eff9-122">COMClassicVTableDestroyed-Methode</span><span class="sxs-lookup"><span data-stu-id="7eff9-122">COMClassicVTableDestroyed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtabledestroyed-method.md)
