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
# <a name="icorprofilercallbackcomclassicvtabledestroyed-method"></a><span data-ttu-id="bc8ba-102">ICorProfilerCallback::COMClassicVTableDestroyed-Methode</span><span class="sxs-lookup"><span data-stu-id="bc8ba-102">ICorProfilerCallback::COMClassicVTableDestroyed Method</span></span>
<span data-ttu-id="bc8ba-103">Benachrichtigt den Profiler, dass eine COM-Interop-Vtable zerstört wird.</span><span class="sxs-lookup"><span data-stu-id="bc8ba-103">Notifies the profiler that a COM interop vtable is being destroyed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bc8ba-104">Dieser Rückruf wird wahrscheinlich nie durchgeführt, da die Zerstörung von vtables sehr nahe beim Herunterfahren auftritt.</span><span class="sxs-lookup"><span data-stu-id="bc8ba-104">This callback is likely never to occur, because the destruction of vtables occurs very close to shutdown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc8ba-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="bc8ba-105">Syntax</span></span>  
  
```cpp  
HRESULT COMClassicVTableDestroyed(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc8ba-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="bc8ba-106">Parameters</span></span>  
 `wrappedClassId`  
 <span data-ttu-id="bc8ba-107">in Die ID der Klasse, für die diese Vtable erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="bc8ba-107">[in] The ID of the class for which this vtable was created.</span></span>  
  
 `implementedIID`  
 <span data-ttu-id="bc8ba-108">in Die ID der Schnittstelle, die von der-Klasse implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="bc8ba-108">[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="bc8ba-109">Dieser Wert kann NULL sein, wenn die Schnittstelle nur intern ist.</span><span class="sxs-lookup"><span data-stu-id="bc8ba-109">This value may be NULL if the interface is internal only.</span></span>  
  
 `pVTable`  
 <span data-ttu-id="bc8ba-110">in Ein Zeiger auf den Anfang der vtable.</span><span class="sxs-lookup"><span data-stu-id="bc8ba-110">[in] A pointer to the start of the vtable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc8ba-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bc8ba-111">Remarks</span></span>  
 <span data-ttu-id="bc8ba-112">Der Profiler sollte in seiner Implementierung dieser Methode nicht blockieren, da sich der Stapel möglicherweise nicht in einem Zustand befindet, der Garbage Collection zulässt, und daher können präemptiv Garbage Collection nicht aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="bc8ba-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="bc8ba-113">Wenn der Profiler hier blockiert wird und Garbage Collection versucht wird, wird die Laufzeit blockiert, bis dieser Rückruf zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="bc8ba-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="bc8ba-114">Die Implementierung dieser Methode des Profilers sollte nicht in verwalteten Code oder auf irgendeine Weise eine verwaltete Speicher Belegung verursachen.</span><span class="sxs-lookup"><span data-stu-id="bc8ba-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc8ba-115">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="bc8ba-115">Requirements</span></span>  
 <span data-ttu-id="bc8ba-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc8ba-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc8ba-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bc8ba-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bc8ba-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc8ba-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc8ba-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc8ba-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc8ba-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc8ba-120">See also</span></span>

- [<span data-ttu-id="bc8ba-121">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bc8ba-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="bc8ba-122">COMClassicVTableCreated-Methode</span><span class="sxs-lookup"><span data-stu-id="bc8ba-122">COMClassicVTableCreated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtablecreated-method.md)
