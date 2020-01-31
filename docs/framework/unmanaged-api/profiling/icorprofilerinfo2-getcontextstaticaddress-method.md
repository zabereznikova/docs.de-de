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
ms.openlocfilehash: d99e5000cdd0d7252764554025815dbace2289f4
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868680"
---
# <a name="icorprofilerinfo2getcontextstaticaddress-method"></a><span data-ttu-id="13b7c-102">ICorProfilerInfo2::GetContextStaticAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="13b7c-102">ICorProfilerInfo2::GetContextStaticAddress Method</span></span>
<span data-ttu-id="13b7c-103">Ruft die Adresse für das angegebene Kontext statische Feld ab, das sich im Gültigkeitsbereich des angegebenen Kontexts befindet.</span><span class="sxs-lookup"><span data-stu-id="13b7c-103">Gets the address for the specified context-static field that is in the scope of the specified context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13b7c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="13b7c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetContextStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] ContextID contextId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13b7c-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="13b7c-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="13b7c-106">in Die ID der Klasse, die das angeforderte Kontext statische Feld enthält.</span><span class="sxs-lookup"><span data-stu-id="13b7c-106">[in] The ID of the class that contains the requested context-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="13b7c-107">in Das Metadatentoken für das angeforderte Kontext statische Feld.</span><span class="sxs-lookup"><span data-stu-id="13b7c-107">[in] The metadata token for the requested context-static field.</span></span>  
  
 `contextId`  
 <span data-ttu-id="13b7c-108">in Die ID des Kontexts, bei dem es sich um den Bereich für das angeforderte Kontext statische Feld handelt.</span><span class="sxs-lookup"><span data-stu-id="13b7c-108">[in] The ID of the context that is the scope for the requested context-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="13b7c-109">vorgenommen Ein Zeiger auf die Adresse des statischen Felds, das sich im angegebenen Kontext befindet.</span><span class="sxs-lookup"><span data-stu-id="13b7c-109">[out] A pointer to the address of the static field that is within the specified context.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13b7c-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="13b7c-110">Remarks</span></span>  
 <span data-ttu-id="13b7c-111">Die `GetContextStaticAddress`-Methode kann eine der folgenden Methoden zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="13b7c-111">The `GetContextStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="13b7c-112">Ein CORPROF_E_DATAINCOMPLETE HRESULT, wenn dem angegebenen statischen Feld keine Adresse im angegebenen Kontext zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="13b7c-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="13b7c-113">Die Adressen von Objekten, die sich möglicherweise im Garbage Collection Heap befinden.</span><span class="sxs-lookup"><span data-stu-id="13b7c-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="13b7c-114">Diese Adressen können nach Garbage Collection ungültig werden. Daher sollten Profiler nach Garbage Collection nicht davon ausgehen, dass Sie gültig sind.</span><span class="sxs-lookup"><span data-stu-id="13b7c-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="13b7c-115">Bevor der Klassenkonstruktor einer Klasse abgeschlossen ist, gibt `GetContextStaticAddress` CORPROF_E_DATAINCOMPLETE für alle statischen Felder zurück, obwohl einige der statischen Felder möglicherweise bereits initialisiert sind und Garbage Collection Objekte rooting.</span><span class="sxs-lookup"><span data-stu-id="13b7c-115">Before a class’s class constructor is completed, `GetContextStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13b7c-116">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="13b7c-116">Requirements</span></span>  
 <span data-ttu-id="13b7c-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13b7c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13b7c-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="13b7c-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="13b7c-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13b7c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13b7c-120">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13b7c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13b7c-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13b7c-121">See also</span></span>

- [<span data-ttu-id="13b7c-122">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="13b7c-122">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="13b7c-123">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="13b7c-123">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
