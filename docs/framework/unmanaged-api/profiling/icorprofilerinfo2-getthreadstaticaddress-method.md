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
ms.openlocfilehash: a38c8323157cee866ac0ecab97532b9b72a932b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454125"
---
# <a name="icorprofilerinfo2getthreadstaticaddress-method"></a><span data-ttu-id="f272d-102">ICorProfilerInfo2::GetThreadStaticAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="f272d-102">ICorProfilerInfo2::GetThreadStaticAddress Method</span></span>
<span data-ttu-id="f272d-103">Ruft die Adresse des angegebenen threadstatischen Felds, die im Bereich des angegebenen Threads ist.</span><span class="sxs-lookup"><span data-stu-id="f272d-103">Gets the address of the specified thread-static field that is in the scope of the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f272d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f272d-104">Syntax</span></span>  
  
```  
HRESULT GetThreadStaticAddress(  
    [in] ClassID     classId,  
    [in] mdFieldDef  fieldToken,  
    [in] ThreadID    threadId,  
    [out] void       **ppAddress);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f272d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f272d-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="f272d-106">[in] Die ID der Klasse, die das angeforderte threadstatische Feld enthält.</span><span class="sxs-lookup"><span data-stu-id="f272d-106">[in] The ID of the class that contains the requested thread-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="f272d-107">[in] Das Metadatentoken für die angeforderte threadstatische Feld.</span><span class="sxs-lookup"><span data-stu-id="f272d-107">[in] The metadata token for the requested thread-static field.</span></span>  
  
 `threadId`  
 <span data-ttu-id="f272d-108">[in] Die ID des Threads, die den Bereich für die angeforderten statischen Felds ist.</span><span class="sxs-lookup"><span data-stu-id="f272d-108">[in] The ID of the thread that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="f272d-109">[out] Ein Zeiger auf die Adresse des statischen Felds, das innerhalb des angegebenen Threads ist.</span><span class="sxs-lookup"><span data-stu-id="f272d-109">[out] A pointer to the address of the static field that is within the specified thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f272d-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f272d-110">Remarks</span></span>  
 <span data-ttu-id="f272d-111">Die `GetThreadStaticAddress` Methode kann einen der folgenden zurück:</span><span class="sxs-lookup"><span data-stu-id="f272d-111">The `GetThreadStaticAddress` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="f272d-112">Ein CORPROF_E_DATAINCOMPLETE-HRESULT, wenn das angegebene statische Feld eine Adresse im angegebenen Kontext nicht zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="f272d-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="f272d-113">Die Adressen von Objekten, die möglicherweise im Garbage Collection-Heap.</span><span class="sxs-lookup"><span data-stu-id="f272d-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="f272d-114">Diese Adressen möglicherweise ungültig, nach der Garbagecollection, sodass nach dem Garbage Collection Profiler nicht annehmen sollten, dass sie gültig sind.</span><span class="sxs-lookup"><span data-stu-id="f272d-114">These addresses may become invalid after garbage collection, so after garbage collection profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="f272d-115">Vor dem Abschluss einer Klasse Klassenkonstruktor `GetThreadStaticAddress` wird CORPROF_E_DATAINCOMPLETE für alle seine statischen Felder zurück, obwohl einige statische Felder möglicherweise bereits initialisiert und rooting Garbage Collection-Objekten.</span><span class="sxs-lookup"><span data-stu-id="f272d-115">Before a class’s class constructor is completed, `GetThreadStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f272d-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f272d-116">Requirements</span></span>  
 <span data-ttu-id="f272d-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f272d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f272d-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f272d-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f272d-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f272d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f272d-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f272d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f272d-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f272d-121">See Also</span></span>  
 [<span data-ttu-id="f272d-122">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f272d-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="f272d-123">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f272d-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
