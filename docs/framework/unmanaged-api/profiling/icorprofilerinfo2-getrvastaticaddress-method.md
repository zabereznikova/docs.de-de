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
ms.openlocfilehash: db768c97a2d1a0fd5ee42ecfb121fb96d3092e79
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433024"
---
# <a name="icorprofilerinfo2getrvastaticaddress-method"></a><span data-ttu-id="16321-102">ICorProfilerInfo2::GetRVAStaticAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="16321-102">ICorProfilerInfo2::GetRVAStaticAddress Method</span></span>
<span data-ttu-id="16321-103">Ruft die Adresse des angegebenen statischen Felds der relativen virtuellen Adresse (RVA) ab.</span><span class="sxs-lookup"><span data-stu-id="16321-103">Gets the address of the specified relative virtual address (RVA) static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16321-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="16321-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRVAStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16321-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="16321-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="16321-106">in Die ID der Klasse, die das angeforderte RVA-statische Feld enthält.</span><span class="sxs-lookup"><span data-stu-id="16321-106">[in] The ID of the class that contains the requested RVA-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="16321-107">in Metadatentoken für das angeforderte RVA-static-Feld.</span><span class="sxs-lookup"><span data-stu-id="16321-107">[in] Metadata token for the requested RVA-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="16321-108">vorgenommen Ein Zeiger auf die Adresse des Felds RVA-static.</span><span class="sxs-lookup"><span data-stu-id="16321-108">[out] A pointer to the address of the RVA-static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16321-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="16321-109">Remarks</span></span>  
 <span data-ttu-id="16321-110">Die `GetRVAStaticAddress`-Methode kann eine der folgenden Methoden zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="16321-110">The `GetRVAStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="16321-111">Ein CORPROF_E_DATAINCOMPLETE HRESULT, wenn dem angegebenen statischen Feld keine Adresse im angegebenen Kontext zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="16321-111">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="16321-112">Die Adressen von Objekten, die sich möglicherweise im Garbage Collection Heap befinden.</span><span class="sxs-lookup"><span data-stu-id="16321-112">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="16321-113">Diese Adressen können nach Garbage Collection ungültig werden. Daher sollten Profiler nach Garbage Collection nicht davon ausgehen, dass Sie gültig sind.</span><span class="sxs-lookup"><span data-stu-id="16321-113">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="16321-114">Bevor der Klassenkonstruktor einer Klasse abgeschlossen ist, werden `GetRVAStaticAddress` für alle statischen Felder CORPROF_E_DATAINCOMPLETE zurückgegeben, obwohl einige der statischen Felder möglicherweise bereits initialisiert wurden und Garbage Collection Objekte als rooting verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="16321-114">Before a class’s class constructor is completed, `GetRVAStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and may be rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16321-115">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="16321-115">Requirements</span></span>  
 <span data-ttu-id="16321-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16321-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16321-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="16321-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="16321-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16321-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16321-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16321-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16321-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16321-120">See also</span></span>

- [<span data-ttu-id="16321-121">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="16321-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="16321-122">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="16321-122">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
