---
title: ICorProfilerInfo2::GetThreadStaticAddress-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetThreadStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetThreadStaticAddress
helpviewer_keywords:
- GetThreadStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetThreadStaticAddress method [.NET Framework profiling]
ms.assetid: 8e7dbf14-98a2-4384-a950-58a7640e59df
topic_type:
- apiref
ms.openlocfilehash: 2c98f67e20ea36d7fbbb31be2e3761594b674c36
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868602"
---
# <a name="icorprofilerinfo2getthreadstaticaddress-method"></a><span data-ttu-id="c9648-102">ICorProfilerInfo2::GetThreadStaticAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="c9648-102">ICorProfilerInfo2::GetThreadStaticAddress Method</span></span>
<span data-ttu-id="c9648-103">Ruft die Adresse des angegebenen Thread statischen Felds ab, das sich im Gültigkeitsbereich des angegebenen Threads befindet.</span><span class="sxs-lookup"><span data-stu-id="c9648-103">Gets the address of the specified thread-static field that is in the scope of the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9648-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c9648-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadStaticAddress(  
    [in] ClassID     classId,  
    [in] mdFieldDef  fieldToken,  
    [in] ThreadID    threadId,  
    [out] void       **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9648-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="c9648-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="c9648-106">in Die ID der Klasse, die das angeforderte Thread statische Feld enthält.</span><span class="sxs-lookup"><span data-stu-id="c9648-106">[in] The ID of the class that contains the requested thread-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="c9648-107">in Das Metadatentoken für das angeforderte Thread statische Feld.</span><span class="sxs-lookup"><span data-stu-id="c9648-107">[in] The metadata token for the requested thread-static field.</span></span>  
  
 `threadId`  
 <span data-ttu-id="c9648-108">in Die ID des Threads, bei dem es sich um den Bereich für das angeforderte statische Feld handelt.</span><span class="sxs-lookup"><span data-stu-id="c9648-108">[in] The ID of the thread that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="c9648-109">vorgenommen Ein Zeiger auf die Adresse des statischen Felds, das sich im angegebenen Thread befindet.</span><span class="sxs-lookup"><span data-stu-id="c9648-109">[out] A pointer to the address of the static field that is within the specified thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9648-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c9648-110">Remarks</span></span>  
 <span data-ttu-id="c9648-111">Die `GetThreadStaticAddress`-Methode kann eine der folgenden Methoden zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="c9648-111">The `GetThreadStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="c9648-112">Ein CORPROF_E_DATAINCOMPLETE HRESULT, wenn dem angegebenen statischen Feld keine Adresse im angegebenen Kontext zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="c9648-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="c9648-113">Die Adressen von Objekten, die sich möglicherweise im Garbage Collection Heap befinden.</span><span class="sxs-lookup"><span data-stu-id="c9648-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="c9648-114">Diese Adressen können nach Garbage Collection ungültig werden, damit Garbage Collection Profiler nicht davon ausgehen, dass Sie gültig sind.</span><span class="sxs-lookup"><span data-stu-id="c9648-114">These addresses may become invalid after garbage collection, so after garbage collection profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="c9648-115">Bevor der Klassenkonstruktor einer Klasse abgeschlossen ist, gibt `GetThreadStaticAddress` CORPROF_E_DATAINCOMPLETE für alle statischen Felder zurück, obwohl einige der statischen Felder möglicherweise bereits initialisiert sind und Garbage Collection Objekte rooting.</span><span class="sxs-lookup"><span data-stu-id="c9648-115">Before a class’s class constructor is completed, `GetThreadStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9648-116">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c9648-116">Requirements</span></span>  
 <span data-ttu-id="c9648-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9648-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9648-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c9648-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c9648-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9648-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9648-120">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9648-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9648-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9648-121">See also</span></span>

- [<span data-ttu-id="c9648-122">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c9648-122">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="c9648-123">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c9648-123">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
