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
ms.openlocfilehash: de0e46f4703479daeb96cb83276ec14150125e7f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64587444"
---
# <a name="icorprofilerinfo2getthreadstaticaddress-method"></a><span data-ttu-id="3d113-102">ICorProfilerInfo2::GetThreadStaticAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="3d113-102">ICorProfilerInfo2::GetThreadStaticAddress Method</span></span>
<span data-ttu-id="3d113-103">Ruft die Adresse des angegebenen threadstatischen Felds, das in den Bereich des angegebenen Threads ist.</span><span class="sxs-lookup"><span data-stu-id="3d113-103">Gets the address of the specified thread-static field that is in the scope of the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d113-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3d113-104">Syntax</span></span>  
  
```  
HRESULT GetThreadStaticAddress(  
    [in] ClassID     classId,  
    [in] mdFieldDef  fieldToken,  
    [in] ThreadID    threadId,  
    [out] void       **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d113-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3d113-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="3d113-106">[in] Die ID der Klasse, die das angeforderte threadstatische Feld enthält.</span><span class="sxs-lookup"><span data-stu-id="3d113-106">[in] The ID of the class that contains the requested thread-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="3d113-107">[in] Das Metadatentoken für das angeforderte threadstatischen Feld.</span><span class="sxs-lookup"><span data-stu-id="3d113-107">[in] The metadata token for the requested thread-static field.</span></span>  
  
 `threadId`  
 <span data-ttu-id="3d113-108">[in] Die ID des Threads, der den Bereich für den angeforderten statischen Feld ist.</span><span class="sxs-lookup"><span data-stu-id="3d113-108">[in] The ID of the thread that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="3d113-109">[out] Ein Zeiger auf die Adresse eines statischen Felds, das in den angegebenen Thread ist.</span><span class="sxs-lookup"><span data-stu-id="3d113-109">[out] A pointer to the address of the static field that is within the specified thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d113-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3d113-110">Remarks</span></span>  
 <span data-ttu-id="3d113-111">Die `GetThreadStaticAddress` Methode gibt möglicherweise einen der folgenden zurück:</span><span class="sxs-lookup"><span data-stu-id="3d113-111">The `GetThreadStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="3d113-112">Ein HRESULT CORPROF_E_DATAINCOMPLETE, wenn das angegebene statische Feld eine Adresse im angegebenen Kontext nicht zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="3d113-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="3d113-113">Die Adressen von Objekten, die möglicherweise in die Garbage Collection-Heap.</span><span class="sxs-lookup"><span data-stu-id="3d113-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="3d113-114">Diese Adressen möglicherweise ungültig, nach der Garbagecollection, sodass nach dem Garbage Collection-Profiler nicht annehmen sollten, dass sie gültig sind.</span><span class="sxs-lookup"><span data-stu-id="3d113-114">These addresses may become invalid after garbage collection, so after garbage collection profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="3d113-115">Vor dem Abschluss einer Klasse Klassenkonstruktor `GetThreadStaticAddress` CORPROF_E_DATAINCOMPLETE zurück für alle seine statische Felder, obwohl einige der statischen Felder bereits initialisiert werden kann und rooting-Garbage Collection-Objekten.</span><span class="sxs-lookup"><span data-stu-id="3d113-115">Before a class’s class constructor is completed, `GetThreadStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d113-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3d113-116">Requirements</span></span>  
 <span data-ttu-id="3d113-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d113-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d113-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3d113-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3d113-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d113-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d113-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d113-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d113-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d113-121">See also</span></span>

- [<span data-ttu-id="3d113-122">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3d113-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="3d113-123">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3d113-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
