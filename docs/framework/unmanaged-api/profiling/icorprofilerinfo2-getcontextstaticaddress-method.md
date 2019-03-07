---
title: ICorProfilerInfo2::GetContextStaticAddress-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 16390317f8a6ea1ee9a3841e35b32e040d12db5d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485121"
---
# <a name="icorprofilerinfo2getcontextstaticaddress-method"></a><span data-ttu-id="e2e0c-102">ICorProfilerInfo2::GetContextStaticAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="e2e0c-102">ICorProfilerInfo2::GetContextStaticAddress Method</span></span>
<span data-ttu-id="e2e0c-103">Ruft die Adresse für das angegebene kontextstatische-Feld, das im Rahmen des angegebenen Kontexts.</span><span class="sxs-lookup"><span data-stu-id="e2e0c-103">Gets the address for the specified context-static field that is in the scope of the specified context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2e0c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e2e0c-104">Syntax</span></span>  
  
```  
HRESULT GetContextStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] ContextID contextId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2e0c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e2e0c-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="e2e0c-106">[in] Die ID der Klasse, die das angeforderte kontextstatische-Feld enthält.</span><span class="sxs-lookup"><span data-stu-id="e2e0c-106">[in] The ID of the class that contains the requested context-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="e2e0c-107">[in] Das Metadatentoken für das angeforderte kontextstatische-Feld.</span><span class="sxs-lookup"><span data-stu-id="e2e0c-107">[in] The metadata token for the requested context-static field.</span></span>  
  
 `contextId`  
 <span data-ttu-id="e2e0c-108">[in] Die ID des Kontexts, der den Bereich für die angeforderte statische Feld des Kontexts ist.</span><span class="sxs-lookup"><span data-stu-id="e2e0c-108">[in] The ID of the context that is the scope for the requested context-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="e2e0c-109">[out] Ein Zeiger auf die Adresse eines statischen Felds, das innerhalb des angegebenen Kontexts.</span><span class="sxs-lookup"><span data-stu-id="e2e0c-109">[out] A pointer to the address of the static field that is within the specified context.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2e0c-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e2e0c-110">Remarks</span></span>  
 <span data-ttu-id="e2e0c-111">Die `GetContextStaticAddress` Methode gibt möglicherweise einen der folgenden zurück:</span><span class="sxs-lookup"><span data-stu-id="e2e0c-111">The `GetContextStaticAddress` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="e2e0c-112">Ein HRESULT CORPROF_E_DATAINCOMPLETE, wenn das angegebene statische Feld eine Adresse im angegebenen Kontext nicht zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="e2e0c-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="e2e0c-113">Die Adressen von Objekten, die möglicherweise in die Garbage Collection-Heap.</span><span class="sxs-lookup"><span data-stu-id="e2e0c-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="e2e0c-114">Diese Adressen können nach der Garbagecollection, ungültig werden. daher nach der Garbagecollection, Profiler nicht davon auszugehen, dass sie gültig sind.</span><span class="sxs-lookup"><span data-stu-id="e2e0c-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="e2e0c-115">Vor dem Abschluss einer Klasse Klassenkonstruktor `GetContextStaticAddress` CORPROF_E_DATAINCOMPLETE zurück für alle seine statische Felder, obwohl einige der statischen Felder bereits initialisiert werden kann und rooting-Garbage Collection-Objekten.</span><span class="sxs-lookup"><span data-stu-id="e2e0c-115">Before a class’s class constructor is completed, `GetContextStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2e0c-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e2e0c-116">Requirements</span></span>  
 <span data-ttu-id="e2e0c-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2e0c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2e0c-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e2e0c-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e2e0c-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2e0c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2e0c-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2e0c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2e0c-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2e0c-121">See also</span></span>
- [<span data-ttu-id="e2e0c-122">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e2e0c-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="e2e0c-123">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e2e0c-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
