---
title: ICorProfilerInfo2::GetThreadStaticAddress-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetThreadStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetThreadStaticAddress
helpviewer_keywords:
- GetThreadStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetThreadStaticAddress method [.NET Framework profiling]
ms.assetid: 8e7dbf14-98a2-4384-a950-58a7640e59df
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e8a842dd531576b1029c3924d12b1a4bd95bde37
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115205"
---
# <a name="icorprofilerinfo2getthreadstaticaddress-method"></a><span data-ttu-id="52340-102">ICorProfilerInfo2::GetThreadStaticAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="52340-102">ICorProfilerInfo2::GetThreadStaticAddress Method</span></span>
<span data-ttu-id="52340-103">Ruft die Adresse des angegebenen threadstatischen Felds, das in den Bereich des angegebenen Threads ist.</span><span class="sxs-lookup"><span data-stu-id="52340-103">Gets the address of the specified thread-static field that is in the scope of the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52340-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="52340-104">Syntax</span></span>  
  
```  
HRESULT GetThreadStaticAddress(  
    [in] ClassID     classId,  
    [in] mdFieldDef  fieldToken,  
    [in] ThreadID    threadId,  
    [out] void       **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52340-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="52340-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="52340-106">[in] Die ID der Klasse, die das angeforderte threadstatische Feld enthält.</span><span class="sxs-lookup"><span data-stu-id="52340-106">[in] The ID of the class that contains the requested thread-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="52340-107">[in] Das Metadatentoken für das angeforderte threadstatischen Feld.</span><span class="sxs-lookup"><span data-stu-id="52340-107">[in] The metadata token for the requested thread-static field.</span></span>  
  
 `threadId`  
 <span data-ttu-id="52340-108">[in] Die ID des Threads, der den Bereich für den angeforderten statischen Feld ist.</span><span class="sxs-lookup"><span data-stu-id="52340-108">[in] The ID of the thread that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="52340-109">[out] Ein Zeiger auf die Adresse eines statischen Felds, das in den angegebenen Thread ist.</span><span class="sxs-lookup"><span data-stu-id="52340-109">[out] A pointer to the address of the static field that is within the specified thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52340-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="52340-110">Remarks</span></span>  
 <span data-ttu-id="52340-111">Die `GetThreadStaticAddress` Methode gibt möglicherweise einen der folgenden zurück:</span><span class="sxs-lookup"><span data-stu-id="52340-111">The `GetThreadStaticAddress` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="52340-112">Ein HRESULT CORPROF_E_DATAINCOMPLETE, wenn das angegebene statische Feld eine Adresse im angegebenen Kontext nicht zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="52340-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="52340-113">Die Adressen von Objekten, die möglicherweise in die Garbage Collection-Heap.</span><span class="sxs-lookup"><span data-stu-id="52340-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="52340-114">Diese Adressen möglicherweise ungültig, nach der Garbagecollection, sodass nach dem Garbage Collection-Profiler nicht annehmen sollten, dass sie gültig sind.</span><span class="sxs-lookup"><span data-stu-id="52340-114">These addresses may become invalid after garbage collection, so after garbage collection profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="52340-115">Vor dem Abschluss einer Klasse Klassenkonstruktor `GetThreadStaticAddress` CORPROF_E_DATAINCOMPLETE zurück für alle seine statische Felder, obwohl einige der statischen Felder bereits initialisiert werden kann und rooting-Garbage Collection-Objekten.</span><span class="sxs-lookup"><span data-stu-id="52340-115">Before a class’s class constructor is completed, `GetThreadStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52340-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="52340-116">Requirements</span></span>  
 <span data-ttu-id="52340-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52340-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52340-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="52340-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="52340-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52340-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52340-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52340-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52340-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52340-121">See also</span></span>

- [<span data-ttu-id="52340-122">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="52340-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="52340-123">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="52340-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
