---
title: ICorProfilerCallback::COMClassicVTableDestroyed-Methode
ms.date: 03/30/2017
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
ms.openlocfilehash: 0b0683d43778c4733b476e9feef459207b9d1ee6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445026"
---
# <a name="icorprofilercallbackcomclassicvtabledestroyed-method"></a><span data-ttu-id="959f6-102">ICorProfilerCallback::COMClassicVTableDestroyed-Methode</span><span class="sxs-lookup"><span data-stu-id="959f6-102">ICorProfilerCallback::COMClassicVTableDestroyed Method</span></span>
<span data-ttu-id="959f6-103">Notifies the profiler that a COM interop vtable is being destroyed.</span><span class="sxs-lookup"><span data-stu-id="959f6-103">Notifies the profiler that a COM interop vtable is being destroyed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="959f6-104">This callback is likely never to occur, because the destruction of vtables occurs very close to shutdown.</span><span class="sxs-lookup"><span data-stu-id="959f6-104">This callback is likely never to occur, because the destruction of vtables occurs very close to shutdown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="959f6-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="959f6-105">Syntax</span></span>  
  
```cpp  
HRESULT COMClassicVTableDestroyed(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="959f6-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="959f6-106">Parameters</span></span>  
 `wrappedClassId`  
 <span data-ttu-id="959f6-107">[in] The ID of the class for which this vtable was created.</span><span class="sxs-lookup"><span data-stu-id="959f6-107">[in] The ID of the class for which this vtable was created.</span></span>  
  
 `implementedIID`  
 <span data-ttu-id="959f6-108">[in] The ID of the interface implemented by the class.</span><span class="sxs-lookup"><span data-stu-id="959f6-108">[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="959f6-109">This value may be NULL if the interface is internal only.</span><span class="sxs-lookup"><span data-stu-id="959f6-109">This value may be NULL if the interface is internal only.</span></span>  
  
 `pVTable`  
 <span data-ttu-id="959f6-110">[in] A pointer to the start of the vtable.</span><span class="sxs-lookup"><span data-stu-id="959f6-110">[in] A pointer to the start of the vtable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="959f6-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="959f6-111">Remarks</span></span>  
 <span data-ttu-id="959f6-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span><span class="sxs-lookup"><span data-stu-id="959f6-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="959f6-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span><span class="sxs-lookup"><span data-stu-id="959f6-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="959f6-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span><span class="sxs-lookup"><span data-stu-id="959f6-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="959f6-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="959f6-115">Requirements</span></span>  
 <span data-ttu-id="959f6-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="959f6-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="959f6-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="959f6-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="959f6-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="959f6-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="959f6-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="959f6-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="959f6-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="959f6-120">See also</span></span>

- [<span data-ttu-id="959f6-121">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="959f6-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="959f6-122">COMClassicVTableCreated-Methode</span><span class="sxs-lookup"><span data-stu-id="959f6-122">COMClassicVTableCreated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtablecreated-method.md)
