---
title: ICorProfilerInfo3::GetThreadStaticAddress2-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetThreadStaticAddress2 Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetThreadStaticAddress2
helpviewer_keywords:
- ICorProfilerInfo3::GetThreadStaticAddress2 method [.NET Framework profiling]
- GetThreadStaticAddress2 method [.NET Framework profiling]
ms.assetid: a9608861-ae64-4467-8a73-be05ad34beac
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 49139f5b1f65bc2e258362d9b47f4e0d44cc6894
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481520"
---
# <a name="icorprofilerinfo3getthreadstaticaddress2-method"></a><span data-ttu-id="a2a7a-102">ICorProfilerInfo3::GetThreadStaticAddress2-Methode</span><span class="sxs-lookup"><span data-stu-id="a2a7a-102">ICorProfilerInfo3::GetThreadStaticAddress2 Method</span></span>
<span data-ttu-id="a2a7a-103">Ruft die Adresse des angegebenen threadstatischen Felds im Bereich des angegebenen Threads und der Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="a2a7a-103">Gets the address of the specified thread-static field that is in the scope of the specified thread and application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2a7a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a2a7a-104">Syntax</span></span>  
  
```  
HRESULT GetThreadStaticAddress2(  
                [in] ClassID classId,  
                [in] mdFieldDef fieldToken,  
                [in] AppDomainID appDomainId,  
                [in] ThreadID threadId,  
                [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2a7a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a2a7a-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="a2a7a-106">[in] Die ID der Klasse, die das angeforderte threadstatische Feld enthält.</span><span class="sxs-lookup"><span data-stu-id="a2a7a-106">[in] The ID of the class that contains the requested thread-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="a2a7a-107">[in] Das Metadatentoken für das angeforderte threadstatischen Feld.</span><span class="sxs-lookup"><span data-stu-id="a2a7a-107">[in] The metadata token for the requested thread-static field.</span></span>  
  
 `appDomainId`  
 <span data-ttu-id="a2a7a-108">[in] Die ID der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="a2a7a-108">[in] The ID of the application domain.</span></span>  
  
 `threadId`  
 <span data-ttu-id="a2a7a-109">[in] Die ID des Threads, der den Bereich für den angeforderten statischen Feld ist.</span><span class="sxs-lookup"><span data-stu-id="a2a7a-109">[in] The ID of the thread that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="a2a7a-110">[out] Ein Zeiger auf die Adresse eines statischen Felds, das in den angegebenen Thread ist.</span><span class="sxs-lookup"><span data-stu-id="a2a7a-110">[out] A pointer to the address of the static field that is within the specified thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2a7a-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a2a7a-111">Remarks</span></span>  
 <span data-ttu-id="a2a7a-112">Die `GetThreadStaticAddress2` Methode gibt möglicherweise einen der folgenden zurück:</span><span class="sxs-lookup"><span data-stu-id="a2a7a-112">The `GetThreadStaticAddress2` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="a2a7a-113">Ein HRESULT CORPROF_E_DATAINCOMPLETE, wenn das angegebene statische Feld eine Adresse im angegebenen Kontext nicht zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="a2a7a-113">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="a2a7a-114">Die Adressen von Objekten, die möglicherweise in die Garbage Collection-Heap.</span><span class="sxs-lookup"><span data-stu-id="a2a7a-114">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="a2a7a-115">Diese Adressen können nach der Garbagecollection, ungültig werden. daher nach der Garbagecollection, Profiler nicht davon auszugehen, dass sie gültig sind.</span><span class="sxs-lookup"><span data-stu-id="a2a7a-115">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="a2a7a-116">Vor dem Abschluss einer Klasse Klassenkonstruktor `GetThreadStaticAddress2` CORPROF_E_DATAINCOMPLETE zurück für alle seine statische Felder, obwohl einige der statischen Felder bereits initialisiert werden kann und rooting-Garbage Collection-Objekten.</span><span class="sxs-lookup"><span data-stu-id="a2a7a-116">Before a class’s class constructor is completed, `GetThreadStaticAddress2` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
 <span data-ttu-id="a2a7a-117">Die [ICorProfilerInfo2:: GetThreadStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md) Methode ähnelt der `GetThreadStaticAddress2` -Methode, jedoch keine Anwendung domänenargument akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="a2a7a-117">The [ICorProfilerInfo2::GetThreadStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md) method is similar to the `GetThreadStaticAddress2` method, but does not accept an application domain argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2a7a-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a2a7a-118">Requirements</span></span>  
 <span data-ttu-id="a2a7a-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2a7a-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2a7a-120">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a2a7a-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a2a7a-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2a7a-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2a7a-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2a7a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2a7a-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2a7a-123">See also</span></span>
- [<span data-ttu-id="a2a7a-124">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a2a7a-124">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="a2a7a-125">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="a2a7a-125">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="a2a7a-126">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="a2a7a-126">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
