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
ms.openlocfilehash: c4d1f2467927e64ae08c0e7d8067c2ce96b95522
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700209"
---
# <a name="icorprofilercallbackcomclassicvtablecreated-method"></a><span data-ttu-id="9e5ce-102">ICorProfilerCallback::COMClassicVTableCreated-Methode</span><span class="sxs-lookup"><span data-stu-id="9e5ce-102">ICorProfilerCallback::COMClassicVTableCreated Method</span></span>

<span data-ttu-id="9e5ce-103">Benachrichtigt den Profiler, dass eine COM-Interop-Vtable für die angegebene IID und Klasse erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="9e5ce-103">Notifies the profiler that a COM interop vtable for the specified IID and class has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e5ce-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9e5ce-104">Syntax</span></span>  
  
```cpp  
HRESULT COMClassicVTableCreated(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable,  
    [in] ULONG   cSlots);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e5ce-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9e5ce-105">Parameters</span></span>

- `wrappedClasId`

  <span data-ttu-id="9e5ce-106">\[in] die ID der Klasse, für die die Vtable erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="9e5ce-106">\[in] The ID of the class for which the vtable has been created.</span></span>

- `implementedIID`

  <span data-ttu-id="9e5ce-107">\[in] die ID der Schnittstelle, die von der-Klasse implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="9e5ce-107">\[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="9e5ce-108">Dieser Wert kann NULL sein, wenn die Schnittstelle nur intern ist.</span><span class="sxs-lookup"><span data-stu-id="9e5ce-108">This value may be NULL if the interface is internal only.</span></span>

- `pVTable`

  <span data-ttu-id="9e5ce-109">\[in] ein Zeiger auf den Anfang der vtable.</span><span class="sxs-lookup"><span data-stu-id="9e5ce-109">\[in] A pointer to the start of the vtable.</span></span>

- `cSlots`

  <span data-ttu-id="9e5ce-110">\[in] die Anzahl der Slots in der vtable.</span><span class="sxs-lookup"><span data-stu-id="9e5ce-110">\[in] The number of slots that are in the vtable.</span></span>

## <a name="remarks"></a><span data-ttu-id="9e5ce-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9e5ce-111">Remarks</span></span>  

 <span data-ttu-id="9e5ce-112">Der Profiler sollte in seiner Implementierung dieser Methode nicht blockieren, da sich der Stapel möglicherweise nicht in einem Zustand befindet, der Garbage Collection zulässt, und daher können präemptiv Garbage Collection nicht aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="9e5ce-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="9e5ce-113">Wenn der Profiler hier blockiert wird und Garbage Collection versucht wird, wird die Laufzeit blockiert, bis dieser Rückruf zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="9e5ce-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="9e5ce-114">Die Implementierung dieser Methode des Profilers sollte nicht in verwalteten Code oder auf irgendeine Weise eine verwaltete Speicher Belegung verursachen.</span><span class="sxs-lookup"><span data-stu-id="9e5ce-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e5ce-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9e5ce-115">Requirements</span></span>  

 <span data-ttu-id="9e5ce-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e5ce-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e5ce-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9e5ce-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9e5ce-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e5ce-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e5ce-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e5ce-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e5ce-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9e5ce-120">See also</span></span>

- [<span data-ttu-id="9e5ce-121">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9e5ce-121">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="9e5ce-122">COMClassicVTableDestroyed-Methode</span><span class="sxs-lookup"><span data-stu-id="9e5ce-122">COMClassicVTableDestroyed Method</span></span>](icorprofilercallback-comclassicvtabledestroyed-method.md)
