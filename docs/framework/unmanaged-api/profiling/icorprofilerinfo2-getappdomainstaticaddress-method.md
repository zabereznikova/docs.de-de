---
title: ICorProfilerInfo2::GetAppDomainStaticAddress-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetAppDomainStaticAddress
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetAppDomainStaticAddress
helpviewer_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress method [.NET Framework profiling]
- GetAppDomainStaticAddress method [.NET Framework profiling]
ms.assetid: 2a9e0ea7-a9e2-4817-b1c4-fcf15b215ea9
topic_type: apiref
caps.latest.revision: "22"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2fad6cccc3992f001780bf8bd1a4c879dc6aa754
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getappdomainstaticaddress-method"></a><span data-ttu-id="d012c-102">ICorProfilerInfo2::GetAppDomainStaticAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="d012c-102">ICorProfilerInfo2::GetAppDomainStaticAddress Method</span></span>
<span data-ttu-id="d012c-103">Ruft die Adresse des Felds Domäne statische angegebenen Anwendung, die im Rahmen der angegebenen Anwendungsdomäne ab.</span><span class="sxs-lookup"><span data-stu-id="d012c-103">Gets the address of the specified application domain-static field that is in the scope of the specified application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d012c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d012c-104">Syntax</span></span>  
  
```  
RESULT GetAppDomainStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] AppDomainID appDomainId,  
    [out] void **ppAddress);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d012c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d012c-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="d012c-106">[in] Die Klassen-ID der Klasse, die die angeforderte Domäne statische Feld enthält.</span><span class="sxs-lookup"><span data-stu-id="d012c-106">[in] The class ID of the class that contains the requested application domain-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="d012c-107">[in] Das Metadatentoken für die angeforderte Domäne statische Feld.</span><span class="sxs-lookup"><span data-stu-id="d012c-107">[in] The metadata token for the requested application domain-static field.</span></span>  
  
 `appDomainId`  
 <span data-ttu-id="d012c-108">[in] Die ID der Anwendungsdomäne, die den Bereich für die angeforderten statischen Felds ist.</span><span class="sxs-lookup"><span data-stu-id="d012c-108">[in] The ID of the application domain that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="d012c-109">[out] Ein Zeiger auf die Adresse des statischen Felds, das in die angegebene Anwendungsdomäne ist.</span><span class="sxs-lookup"><span data-stu-id="d012c-109">[out] A pointer to the address of the static field that is within the specified application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d012c-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d012c-110">Remarks</span></span>  
 <span data-ttu-id="d012c-111">Die `GetAppDomainStaticAddress` Methode kann einen der folgenden zurück:</span><span class="sxs-lookup"><span data-stu-id="d012c-111">The `GetAppDomainStaticAddress` method may return one of the following:</span></span>  
  
-   <span data-ttu-id="d012c-112">Ein CORPROF_E_DATAINCOMPLETE-HRESULT, wenn das angegebene statische Feld eine Adresse im angegebenen Kontext nicht zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="d012c-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
-   <span data-ttu-id="d012c-113">Die Adressen von Objekten, die möglicherweise im Garbage Collection-Heap.</span><span class="sxs-lookup"><span data-stu-id="d012c-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="d012c-114">Diese Adressen möglicherweise nach der Garbagecollection, ungültig werden, damit nach der Garbagecollection Profiler nicht annehmen soll, dass sie gültig sind.</span><span class="sxs-lookup"><span data-stu-id="d012c-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="d012c-115">Vor dem Abschluss einer Klasse Klassenkonstruktor `GetAppDomainStaticAddress` wird CORPROF_E_DATAINCOMPLETE für alle seine statischen Felder zurück, obwohl einige statische Felder möglicherweise bereits initialisiert und rooting Garbage Collection-Objekten.</span><span class="sxs-lookup"><span data-stu-id="d012c-115">Before a class’s class constructor is completed, `GetAppDomainStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d012c-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d012c-116">Requirements</span></span>  
 <span data-ttu-id="d012c-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d012c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d012c-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d012c-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d012c-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d012c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d012c-120">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d012c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d012c-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d012c-121">See Also</span></span>  
 [<span data-ttu-id="d012c-122">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d012c-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="d012c-123">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d012c-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
