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
ms.openlocfilehash: a51d88af20b3abbbe2f80134473ec1ba1b7a4b17
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454547"
---
# <a name="icorprofilerinfo3getthreadstaticaddress2-method"></a><span data-ttu-id="6f720-102">ICorProfilerInfo3::GetThreadStaticAddress2-Methode</span><span class="sxs-lookup"><span data-stu-id="6f720-102">ICorProfilerInfo3::GetThreadStaticAddress2 Method</span></span>
<span data-ttu-id="6f720-103">Ruft die Adresse des angegebenen threadstatischen Felds im Bereich des angegebenen Threads und der Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="6f720-103">Gets the address of the specified thread-static field that is in the scope of the specified thread and application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f720-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f720-104">Syntax</span></span>  
  
```  
HRESULT GetThreadStaticAddress2(  
                [in] ClassID classId,  
                [in] mdFieldDef fieldToken,  
                [in] AppDomainID appDomainId,  
                [in] ThreadID threadId,  
                [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6f720-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6f720-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="6f720-106">[in] Die ID der Klasse, die das angeforderte threadstatische Feld enthält.</span><span class="sxs-lookup"><span data-stu-id="6f720-106">[in] The ID of the class that contains the requested thread-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="6f720-107">[in] Das Metadatentoken für die angeforderte threadstatische Feld.</span><span class="sxs-lookup"><span data-stu-id="6f720-107">[in] The metadata token for the requested thread-static field.</span></span>  
  
 `appDomainId`  
 <span data-ttu-id="6f720-108">[in] Die ID der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="6f720-108">[in] The ID of the application domain.</span></span>  
  
 `threadId`  
 <span data-ttu-id="6f720-109">[in] Die ID des Threads, die den Bereich für die angeforderten statischen Felds ist.</span><span class="sxs-lookup"><span data-stu-id="6f720-109">[in] The ID of the thread that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="6f720-110">[out] Ein Zeiger auf die Adresse des statischen Felds, das innerhalb des angegebenen Threads ist.</span><span class="sxs-lookup"><span data-stu-id="6f720-110">[out] A pointer to the address of the static field that is within the specified thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f720-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6f720-111">Remarks</span></span>  
 <span data-ttu-id="6f720-112">Die `GetThreadStaticAddress2` Methode kann einen der folgenden zurück:</span><span class="sxs-lookup"><span data-stu-id="6f720-112">The `GetThreadStaticAddress2` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="6f720-113">Ein CORPROF_E_DATAINCOMPLETE-HRESULT, wenn das angegebene statische Feld eine Adresse im angegebenen Kontext nicht zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="6f720-113">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="6f720-114">Die Adressen von Objekten, die möglicherweise im Garbage Collection-Heap.</span><span class="sxs-lookup"><span data-stu-id="6f720-114">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="6f720-115">Diese Adressen möglicherweise nach der Garbagecollection, ungültig werden, damit nach der Garbagecollection Profiler nicht annehmen soll, dass sie gültig sind.</span><span class="sxs-lookup"><span data-stu-id="6f720-115">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="6f720-116">Vor dem Abschluss einer Klasse Klassenkonstruktor `GetThreadStaticAddress2` wird CORPROF_E_DATAINCOMPLETE für alle seine statischen Felder zurück, obwohl einige statische Felder möglicherweise bereits initialisiert und rooting Garbage Collection-Objekten.</span><span class="sxs-lookup"><span data-stu-id="6f720-116">Before a class’s class constructor is completed, `GetThreadStaticAddress2` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
 <span data-ttu-id="6f720-117">Die [ICorProfilerInfo2:: GetThreadStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md) Methode ist vergleichbar mit der `GetThreadStaticAddress2` -Methode, aber keine Anwendung Domäne Argument akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="6f720-117">The [ICorProfilerInfo2::GetThreadStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md) method is similar to the `GetThreadStaticAddress2` method, but does not accept an application domain argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f720-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6f720-118">Requirements</span></span>  
 <span data-ttu-id="6f720-119">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f720-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f720-120">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6f720-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6f720-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f720-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f720-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f720-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f720-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f720-123">See Also</span></span>  
 [<span data-ttu-id="6f720-124">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6f720-124">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="6f720-125">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="6f720-125">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="6f720-126">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="6f720-126">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
