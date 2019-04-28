---
title: ICorProfilerInfo2::GetAppDomainStaticAddress-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetAppDomainStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress
helpviewer_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress method [.NET Framework profiling]
- GetAppDomainStaticAddress method [.NET Framework profiling]
ms.assetid: 2a9e0ea7-a9e2-4817-b1c4-fcf15b215ea9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2095f02cb23c3580b0a1109e8f0da669f61adabc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789388"
---
# <a name="icorprofilerinfo2getappdomainstaticaddress-method"></a><span data-ttu-id="1df8c-102">ICorProfilerInfo2::GetAppDomainStaticAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="1df8c-102">ICorProfilerInfo2::GetAppDomainStaticAddress Method</span></span>
<span data-ttu-id="1df8c-103">Ruft die Adresse des angegebenen Anwendung Domäne statischen Felds, das im Bereich der angegebenen Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="1df8c-103">Gets the address of the specified application domain-static field that is in the scope of the specified application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1df8c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1df8c-104">Syntax</span></span>  
  
```  
RESULT GetAppDomainStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] AppDomainID appDomainId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1df8c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1df8c-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="1df8c-106">[in] Die Klassen-ID der Klasse, die die angeforderte Domäne statischen Feld enthält.</span><span class="sxs-lookup"><span data-stu-id="1df8c-106">[in] The class ID of the class that contains the requested application domain-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="1df8c-107">[in] Das Metadatentoken für die angeforderte Domäne statischen Feld.</span><span class="sxs-lookup"><span data-stu-id="1df8c-107">[in] The metadata token for the requested application domain-static field.</span></span>  
  
 `appDomainId`  
 <span data-ttu-id="1df8c-108">[in] Die ID der Anwendungsdomäne, die den Bereich für die angeforderte statische Feld.</span><span class="sxs-lookup"><span data-stu-id="1df8c-108">[in] The ID of the application domain that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="1df8c-109">[out] Ein Zeiger auf die Adresse eines statischen Felds, das innerhalb der angegebenen Anwendungsdomäne ist.</span><span class="sxs-lookup"><span data-stu-id="1df8c-109">[out] A pointer to the address of the static field that is within the specified application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1df8c-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1df8c-110">Remarks</span></span>  
 <span data-ttu-id="1df8c-111">Die `GetAppDomainStaticAddress` Methode gibt möglicherweise einen der folgenden zurück:</span><span class="sxs-lookup"><span data-stu-id="1df8c-111">The `GetAppDomainStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="1df8c-112">Ein HRESULT CORPROF_E_DATAINCOMPLETE, wenn das angegebene statische Feld eine Adresse im angegebenen Kontext nicht zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="1df8c-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="1df8c-113">Die Adressen von Objekten, die möglicherweise in die Garbage Collection-Heap.</span><span class="sxs-lookup"><span data-stu-id="1df8c-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="1df8c-114">Diese Adressen können nach der Garbagecollection, ungültig werden. daher nach der Garbagecollection, Profiler nicht davon auszugehen, dass sie gültig sind.</span><span class="sxs-lookup"><span data-stu-id="1df8c-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="1df8c-115">Vor dem Abschluss einer Klasse Klassenkonstruktor `GetAppDomainStaticAddress` CORPROF_E_DATAINCOMPLETE zurück für alle seine statische Felder, obwohl einige der statischen Felder bereits initialisiert werden kann und rooting-Garbage Collection-Objekten.</span><span class="sxs-lookup"><span data-stu-id="1df8c-115">Before a class’s class constructor is completed, `GetAppDomainStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1df8c-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1df8c-116">Requirements</span></span>  
 <span data-ttu-id="1df8c-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1df8c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1df8c-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1df8c-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1df8c-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1df8c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1df8c-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1df8c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1df8c-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1df8c-121">See also</span></span>

- [<span data-ttu-id="1df8c-122">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1df8c-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="1df8c-123">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1df8c-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
