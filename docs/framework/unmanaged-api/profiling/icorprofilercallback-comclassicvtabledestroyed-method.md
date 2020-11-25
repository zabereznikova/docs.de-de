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
ms.openlocfilehash: aa02b4def015d5badfd0003e08bea5289fe58e17
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700183"
---
# <a name="icorprofilercallbackcomclassicvtabledestroyed-method"></a><span data-ttu-id="2d2d8-102">ICorProfilerCallback::COMClassicVTableDestroyed-Methode</span><span class="sxs-lookup"><span data-stu-id="2d2d8-102">ICorProfilerCallback::COMClassicVTableDestroyed Method</span></span>

<span data-ttu-id="2d2d8-103">Benachrichtigt den Profiler, dass eine COM-Interop-Vtable zerstört wird.</span><span class="sxs-lookup"><span data-stu-id="2d2d8-103">Notifies the profiler that a COM interop vtable is being destroyed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2d2d8-104">Dieser Rückruf wird wahrscheinlich nie durchgeführt, da die Zerstörung von vtables sehr nahe beim Herunterfahren auftritt.</span><span class="sxs-lookup"><span data-stu-id="2d2d8-104">This callback is likely never to occur, because the destruction of vtables occurs very close to shutdown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d2d8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d2d8-105">Syntax</span></span>  
  
```cpp  
HRESULT COMClassicVTableDestroyed(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d2d8-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="2d2d8-106">Parameters</span></span>

- `wrappedClassId`

  <span data-ttu-id="2d2d8-107">\[in] die ID der Klasse, für die diese Vtable erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="2d2d8-107">\[in] The ID of the class for which this vtable was created.</span></span>

- `implementedIID`

  <span data-ttu-id="2d2d8-108">\[in] die ID der Schnittstelle, die von der-Klasse implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="2d2d8-108">\[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="2d2d8-109">Dieser Wert kann NULL sein, wenn die Schnittstelle nur intern ist.</span><span class="sxs-lookup"><span data-stu-id="2d2d8-109">This value may be NULL if the interface is internal only.</span></span>

- `pVTable`

  <span data-ttu-id="2d2d8-110">\[in] ein Zeiger auf den Anfang der vtable.</span><span class="sxs-lookup"><span data-stu-id="2d2d8-110">\[in] A pointer to the start of the vtable.</span></span>

## <a name="remarks"></a><span data-ttu-id="2d2d8-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2d2d8-111">Remarks</span></span>  

 <span data-ttu-id="2d2d8-112">Der Profiler sollte in seiner Implementierung dieser Methode nicht blockieren, da sich der Stapel möglicherweise nicht in einem Zustand befindet, der Garbage Collection zulässt, und daher können präemptiv Garbage Collection nicht aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="2d2d8-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="2d2d8-113">Wenn der Profiler hier blockiert wird und Garbage Collection versucht wird, wird die Laufzeit blockiert, bis dieser Rückruf zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2d2d8-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="2d2d8-114">Die Implementierung dieser Methode des Profilers sollte nicht in verwalteten Code oder auf irgendeine Weise eine verwaltete Speicher Belegung verursachen.</span><span class="sxs-lookup"><span data-stu-id="2d2d8-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d2d8-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2d2d8-115">Requirements</span></span>  

 <span data-ttu-id="2d2d8-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d2d8-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d2d8-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2d2d8-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2d2d8-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d2d8-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d2d8-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d2d8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d2d8-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2d2d8-120">See also</span></span>

- [<span data-ttu-id="2d2d8-121">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2d2d8-121">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="2d2d8-122">COMClassicVTableCreated-Methode</span><span class="sxs-lookup"><span data-stu-id="2d2d8-122">COMClassicVTableCreated Method</span></span>](icorprofilercallback-comclassicvtablecreated-method.md)
