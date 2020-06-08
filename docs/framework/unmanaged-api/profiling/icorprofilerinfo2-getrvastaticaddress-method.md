---
title: ICorProfilerInfo2::GetRVAStaticAddress-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetRVAStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetRVAStaticAddress
helpviewer_keywords:
- GetRVAStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetRVAStaticAddress method [.NET Framework profiling]
ms.assetid: a25a8f8b-5cfa-440d-9376-a1a1c3a9fc11
topic_type:
- apiref
ms.openlocfilehash: 525fa2efa39909390d874fb97d9f11e647340ea9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496944"
---
# <a name="icorprofilerinfo2getrvastaticaddress-method"></a><span data-ttu-id="7ccaf-102">ICorProfilerInfo2::GetRVAStaticAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="7ccaf-102">ICorProfilerInfo2::GetRVAStaticAddress Method</span></span>
<span data-ttu-id="7ccaf-103">Ruft die Adresse des angegebenen statischen Felds der relativen virtuellen Adresse (RVA) ab.</span><span class="sxs-lookup"><span data-stu-id="7ccaf-103">Gets the address of the specified relative virtual address (RVA) static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ccaf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7ccaf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRVAStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ccaf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7ccaf-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="7ccaf-106">in Die ID der Klasse, die das angeforderte RVA-statische Feld enthält.</span><span class="sxs-lookup"><span data-stu-id="7ccaf-106">[in] The ID of the class that contains the requested RVA-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="7ccaf-107">in Metadatentoken für das angeforderte RVA-static-Feld.</span><span class="sxs-lookup"><span data-stu-id="7ccaf-107">[in] Metadata token for the requested RVA-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="7ccaf-108">vorgenommen Ein Zeiger auf die Adresse des Felds RVA-static.</span><span class="sxs-lookup"><span data-stu-id="7ccaf-108">[out] A pointer to the address of the RVA-static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ccaf-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7ccaf-109">Remarks</span></span>  
 <span data-ttu-id="7ccaf-110">Die- `GetRVAStaticAddress` Methode kann eine der folgenden Methoden zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="7ccaf-110">The `GetRVAStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="7ccaf-111">Ein CORPROF_E_DATAINCOMPLETE HRESULT, wenn dem angegebenen statischen Feld keine Adresse im angegebenen Kontext zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="7ccaf-111">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="7ccaf-112">Die Adressen von Objekten, die sich möglicherweise im Garbage Collection Heap befinden.</span><span class="sxs-lookup"><span data-stu-id="7ccaf-112">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="7ccaf-113">Diese Adressen können nach Garbage Collection ungültig werden. Daher sollten Profiler nach Garbage Collection nicht davon ausgehen, dass Sie gültig sind.</span><span class="sxs-lookup"><span data-stu-id="7ccaf-113">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="7ccaf-114">Bevor der Klassenkonstruktor einer Klasse abgeschlossen ist, `GetRVAStaticAddress` gibt CORPROF_E_DATAINCOMPLETE für alle statischen Felder zurück, obwohl einige der statischen Felder möglicherweise bereits initialisiert sind und Garbage Collection-Objekten als rooting verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7ccaf-114">Before a class’s class constructor is completed, `GetRVAStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and may be rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ccaf-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7ccaf-115">Requirements</span></span>  
 <span data-ttu-id="7ccaf-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ccaf-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ccaf-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7ccaf-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7ccaf-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ccaf-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ccaf-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ccaf-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ccaf-120">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="7ccaf-120">See also</span></span>

- [<span data-ttu-id="7ccaf-121">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7ccaf-121">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="7ccaf-122">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7ccaf-122">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
