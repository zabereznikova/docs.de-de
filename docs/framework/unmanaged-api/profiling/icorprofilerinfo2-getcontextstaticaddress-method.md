---
title: ICorProfilerInfo2::GetContextStaticAddress-Methode
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
- ICorProfilerInfo2.GetContextStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetContextStaticAddress
helpviewer_keywords:
- GetContextStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetContextStaticAddress method [.NET Framework profiling]
ms.assetid: 2b374116-0972-416a-8cf5-79213129be9a
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e92435927203bb2a75ff92d883470832126da080
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getcontextstaticaddress-method"></a><span data-ttu-id="2cf59-102">ICorProfilerInfo2::GetContextStaticAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="2cf59-102">ICorProfilerInfo2::GetContextStaticAddress Method</span></span>
<span data-ttu-id="2cf59-103">Ruft die Adresse für die angegebenen Kontext statischen Felds im Bereich des angegebenen Kontexts ab.</span><span class="sxs-lookup"><span data-stu-id="2cf59-103">Gets the address for the specified context-static field that is in the scope of the specified context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cf59-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2cf59-104">Syntax</span></span>  
  
```  
HRESULT GetContextStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] ContextID contextId,  
    [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2cf59-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2cf59-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="2cf59-106">[in] Die ID der Klasse, die die angeforderte statischen Kontext-Feld enthält.</span><span class="sxs-lookup"><span data-stu-id="2cf59-106">[in] The ID of the class that contains the requested context-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="2cf59-107">[in] Das Metadatentoken für die angeforderten statischen Kontext-Feld.</span><span class="sxs-lookup"><span data-stu-id="2cf59-107">[in] The metadata token for the requested context-static field.</span></span>  
  
 `contextId`  
 <span data-ttu-id="2cf59-108">[in] Die ID des Kontexts, der den Bereich für die angeforderten statischen Kontext Feld ist.</span><span class="sxs-lookup"><span data-stu-id="2cf59-108">[in] The ID of the context that is the scope for the requested context-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="2cf59-109">[out] Ein Zeiger auf die Adresse des statischen Felds, das innerhalb des angegebenen Kontexts ist.</span><span class="sxs-lookup"><span data-stu-id="2cf59-109">[out] A pointer to the address of the static field that is within the specified context.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2cf59-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2cf59-110">Remarks</span></span>  
 <span data-ttu-id="2cf59-111">Die `GetContextStaticAddress` Methode kann einen der folgenden zurück:</span><span class="sxs-lookup"><span data-stu-id="2cf59-111">The `GetContextStaticAddress` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="2cf59-112">Ein CORPROF_E_DATAINCOMPLETE-HRESULT, wenn das angegebene statische Feld eine Adresse im angegebenen Kontext nicht zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="2cf59-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="2cf59-113">Die Adressen von Objekten, die möglicherweise im Garbage Collection-Heap.</span><span class="sxs-lookup"><span data-stu-id="2cf59-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="2cf59-114">Diese Adressen möglicherweise nach der Garbagecollection, ungültig werden, damit nach der Garbagecollection Profiler nicht annehmen soll, dass sie gültig sind.</span><span class="sxs-lookup"><span data-stu-id="2cf59-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="2cf59-115">Vor dem Abschluss einer Klasse Klassenkonstruktor `GetContextStaticAddress` wird CORPROF_E_DATAINCOMPLETE für alle seine statischen Felder zurück, obwohl einige statische Felder möglicherweise bereits initialisiert und rooting Garbage Collection-Objekten.</span><span class="sxs-lookup"><span data-stu-id="2cf59-115">Before a class’s class constructor is completed, `GetContextStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cf59-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2cf59-116">Requirements</span></span>  
 <span data-ttu-id="2cf59-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2cf59-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cf59-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2cf59-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2cf59-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2cf59-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2cf59-120">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cf59-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cf59-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2cf59-121">See Also</span></span>  
 [<span data-ttu-id="2cf59-122">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2cf59-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="2cf59-123">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2cf59-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
