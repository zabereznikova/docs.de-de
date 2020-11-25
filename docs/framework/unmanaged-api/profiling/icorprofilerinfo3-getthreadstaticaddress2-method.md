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
ms.openlocfilehash: d8f2788d63f27aac30cf239b410eecea31f09212
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697882"
---
# <a name="icorprofilerinfo3getthreadstaticaddress2-method"></a><span data-ttu-id="5200a-102">ICorProfilerInfo3::GetThreadStaticAddress2-Methode</span><span class="sxs-lookup"><span data-stu-id="5200a-102">ICorProfilerInfo3::GetThreadStaticAddress2 Method</span></span>

<span data-ttu-id="5200a-103">Ruft die Adresse des angegebenen threadstatischen Felds im Bereich des angegebenen Threads und der Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="5200a-103">Gets the address of the specified thread-static field that is in the scope of the specified thread and application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5200a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5200a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadStaticAddress2(  
                [in] ClassID classId,  
                [in] mdFieldDef fieldToken,  
                [in] AppDomainID appDomainId,  
                [in] ThreadID threadId,  
                [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5200a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5200a-105">Parameters</span></span>  

 `classId`  
 <span data-ttu-id="5200a-106">in Die ID der Klasse, die das angeforderte Thread statische Feld enthält.</span><span class="sxs-lookup"><span data-stu-id="5200a-106">[in] The ID of the class that contains the requested thread-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="5200a-107">in Das Metadatentoken für das angeforderte Thread statische Feld.</span><span class="sxs-lookup"><span data-stu-id="5200a-107">[in] The metadata token for the requested thread-static field.</span></span>  
  
 `appDomainId`  
 <span data-ttu-id="5200a-108">[in] Die ID der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="5200a-108">[in] The ID of the application domain.</span></span>  
  
 `threadId`  
 <span data-ttu-id="5200a-109">in Die ID des Threads, bei dem es sich um den Bereich für das angeforderte statische Feld handelt.</span><span class="sxs-lookup"><span data-stu-id="5200a-109">[in] The ID of the thread that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="5200a-110">vorgenommen Ein Zeiger auf die Adresse des statischen Felds, das sich im angegebenen Thread befindet.</span><span class="sxs-lookup"><span data-stu-id="5200a-110">[out] A pointer to the address of the static field that is within the specified thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5200a-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5200a-111">Remarks</span></span>  

 <span data-ttu-id="5200a-112">Die- `GetThreadStaticAddress2` Methode kann eine der folgenden Methoden zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="5200a-112">The `GetThreadStaticAddress2` method may return one of the following:</span></span>  
  
- <span data-ttu-id="5200a-113">Ein CORPROF_E_DATAINCOMPLETE HRESULT, wenn dem angegebenen statischen Feld keine Adresse im angegebenen Kontext zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="5200a-113">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="5200a-114">Die Adressen von Objekten, die sich möglicherweise im Garbage Collection Heap befinden.</span><span class="sxs-lookup"><span data-stu-id="5200a-114">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="5200a-115">Diese Adressen können nach Garbage Collection ungültig werden. Daher sollten Profiler nach Garbage Collection nicht davon ausgehen, dass Sie gültig sind.</span><span class="sxs-lookup"><span data-stu-id="5200a-115">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="5200a-116">Bevor der Klassenkonstruktor einer Klasse abgeschlossen ist, `GetThreadStaticAddress2` gibt CORPROF_E_DATAINCOMPLETE für alle statischen Felder zurück, obwohl einige der statischen Felder möglicherweise bereits initialisiert sind und Garbage Collection Objekte mit rooting erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="5200a-116">Before a class’s class constructor is completed, `GetThreadStaticAddress2` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
 <span data-ttu-id="5200a-117">Die [ICorProfilerInfo2:: GetThreadStaticAddress](icorprofilerinfo2-getthreadstaticaddress-method.md) -Methode ähnelt der- `GetThreadStaticAddress2` Methode, akzeptiert jedoch kein Anwendungs Domänen Argument.</span><span class="sxs-lookup"><span data-stu-id="5200a-117">The [ICorProfilerInfo2::GetThreadStaticAddress](icorprofilerinfo2-getthreadstaticaddress-method.md) method is similar to the `GetThreadStaticAddress2` method, but does not accept an application domain argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5200a-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5200a-118">Requirements</span></span>  

 <span data-ttu-id="5200a-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5200a-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5200a-120">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5200a-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5200a-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5200a-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5200a-122">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5200a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5200a-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5200a-123">See also</span></span>

- [<span data-ttu-id="5200a-124">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5200a-124">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="5200a-125">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="5200a-125">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="5200a-126">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="5200a-126">Profiling</span></span>](index.md)
