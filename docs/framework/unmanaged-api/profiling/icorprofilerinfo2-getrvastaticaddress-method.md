---
title: ICorProfilerInfo2::GetRVAStaticAddress-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetRVAStaticAddress
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetRVAStaticAddress
helpviewer_keywords:
- GetRVAStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetRVAStaticAddress method [.NET Framework profiling]
ms.assetid: a25a8f8b-5cfa-440d-9376-a1a1c3a9fc11
topic_type: apiref
caps.latest.revision: "21"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4320ed3cdd3d17932d03e98d4d35d27adad2532a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getrvastaticaddress-method"></a><span data-ttu-id="12a83-102">ICorProfilerInfo2::GetRVAStaticAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="12a83-102">ICorProfilerInfo2::GetRVAStaticAddress Method</span></span>
<span data-ttu-id="12a83-103">Ruft die Adresse des angegebenen relativen virtuellen Adresse (RVA) statischen Felds ab.</span><span class="sxs-lookup"><span data-stu-id="12a83-103">Gets the address of the specified relative virtual address (RVA) static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12a83-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="12a83-104">Syntax</span></span>  
  
```  
HRESULT GetRVAStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="12a83-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="12a83-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="12a83-106">[in] Die ID der Klasse, die das angeforderte RVA-statische Feld enthält.</span><span class="sxs-lookup"><span data-stu-id="12a83-106">[in] The ID of the class that contains the requested RVA-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="12a83-107">[in] Das Metadatentoken für die angeforderte RVA-statische Feld.</span><span class="sxs-lookup"><span data-stu-id="12a83-107">[in] Metadata token for the requested RVA-static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="12a83-108">[out] Ein Zeiger auf die Adresse des RVA statischen Felds.</span><span class="sxs-lookup"><span data-stu-id="12a83-108">[out] A pointer to the address of the RVA-static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12a83-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="12a83-109">Remarks</span></span>  
 <span data-ttu-id="12a83-110">Die `GetRVAStaticAddress` Methode kann einen der folgenden zurück:</span><span class="sxs-lookup"><span data-stu-id="12a83-110">The `GetRVAStaticAddress` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="12a83-111">Ein CORPROF_E_DATAINCOMPLETE-HRESULT, wenn das angegebene statische Feld eine Adresse im angegebenen Kontext nicht zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="12a83-111">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="12a83-112">Die Adressen von Objekten, die möglicherweise im Garbage Collection-Heap.</span><span class="sxs-lookup"><span data-stu-id="12a83-112">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="12a83-113">Diese Adressen möglicherweise nach der Garbagecollection, ungültig werden, damit nach der Garbagecollection Profiler nicht annehmen soll, dass sie gültig sind.</span><span class="sxs-lookup"><span data-stu-id="12a83-113">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="12a83-114">Vor dem Abschluss einer Klasse Klassenkonstruktor `GetRVAStaticAddress` für alle seine statische Felder, obwohl einige statische Felder sind möglicherweise bereits initialisiert und Garbage Collection-Objekten Stamm CORPROF_E_DATAINCOMPLETE zurück.</span><span class="sxs-lookup"><span data-stu-id="12a83-114">Before a class’s class constructor is completed, `GetRVAStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and may be rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12a83-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="12a83-115">Requirements</span></span>  
 <span data-ttu-id="12a83-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12a83-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12a83-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="12a83-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="12a83-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12a83-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12a83-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12a83-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12a83-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12a83-120">See Also</span></span>  
 [<span data-ttu-id="12a83-121">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="12a83-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="12a83-122">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="12a83-122">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
