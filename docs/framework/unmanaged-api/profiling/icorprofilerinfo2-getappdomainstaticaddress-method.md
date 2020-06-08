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
ms.openlocfilehash: 3dc5f04504cca632892c16d31c92a33935b356e0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497334"
---
# <a name="icorprofilerinfo2getappdomainstaticaddress-method"></a><span data-ttu-id="0ad9e-102">ICorProfilerInfo2::GetAppDomainStaticAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="0ad9e-102">ICorProfilerInfo2::GetAppDomainStaticAddress Method</span></span>
<span data-ttu-id="0ad9e-103">Ruft die Adresse des angegebenen Anwendungs Domänen statischen Felds ab, das sich im Gültigkeitsbereich der angegebenen Anwendungsdomäne befindet.</span><span class="sxs-lookup"><span data-stu-id="0ad9e-103">Gets the address of the specified application domain-static field that is in the scope of the specified application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ad9e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0ad9e-104">Syntax</span></span>  
  
```cpp  
RESULT GetAppDomainStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] AppDomainID appDomainId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ad9e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0ad9e-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="0ad9e-106">in Die Klassen-ID der Klasse, die das angeforderte Feld für die Anwendungsdomäne enthält.</span><span class="sxs-lookup"><span data-stu-id="0ad9e-106">[in] The class ID of the class that contains the requested application domain-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="0ad9e-107">in Das Metadatentoken für das angeforderte Anwendungs Domänen-static-Feld.</span><span class="sxs-lookup"><span data-stu-id="0ad9e-107">[in] The metadata token for the requested application domain-static field.</span></span>  
  
 `appDomainId`  
 <span data-ttu-id="0ad9e-108">in Die ID der Anwendungsdomäne, bei der es sich um den Bereich für das angeforderte statische Feld handelt.</span><span class="sxs-lookup"><span data-stu-id="0ad9e-108">[in] The ID of the application domain that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="0ad9e-109">vorgenommen Ein Zeiger auf die Adresse des statischen Felds, das sich innerhalb der angegebenen Anwendungsdomäne befindet.</span><span class="sxs-lookup"><span data-stu-id="0ad9e-109">[out] A pointer to the address of the static field that is within the specified application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ad9e-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0ad9e-110">Remarks</span></span>  
 <span data-ttu-id="0ad9e-111">Die- `GetAppDomainStaticAddress` Methode kann eine der folgenden Methoden zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="0ad9e-111">The `GetAppDomainStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="0ad9e-112">Ein CORPROF_E_DATAINCOMPLETE HRESULT, wenn dem angegebenen statischen Feld keine Adresse im angegebenen Kontext zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="0ad9e-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="0ad9e-113">Die Adressen von Objekten, die sich möglicherweise im Garbage Collection Heap befinden.</span><span class="sxs-lookup"><span data-stu-id="0ad9e-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="0ad9e-114">Diese Adressen können nach Garbage Collection ungültig werden. Daher sollten Profiler nach Garbage Collection nicht davon ausgehen, dass Sie gültig sind.</span><span class="sxs-lookup"><span data-stu-id="0ad9e-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="0ad9e-115">Bevor der Klassenkonstruktor einer Klasse abgeschlossen ist, `GetAppDomainStaticAddress` gibt CORPROF_E_DATAINCOMPLETE für alle statischen Felder zurück, obwohl einige der statischen Felder möglicherweise bereits initialisiert sind und Garbage Collection Objekte mit rooting erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="0ad9e-115">Before a class’s class constructor is completed, `GetAppDomainStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ad9e-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0ad9e-116">Requirements</span></span>  
 <span data-ttu-id="0ad9e-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ad9e-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ad9e-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0ad9e-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0ad9e-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ad9e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ad9e-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ad9e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ad9e-121">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="0ad9e-121">See also</span></span>

- [<span data-ttu-id="0ad9e-122">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0ad9e-122">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="0ad9e-123">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0ad9e-123">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
