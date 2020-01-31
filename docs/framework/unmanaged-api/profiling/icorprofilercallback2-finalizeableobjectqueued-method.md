---
title: ICorProfilerCallback2::FinalizeableObjectQueued-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.FinalizeableObjectQueued
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::FinalizeableObjectQueued
helpviewer_keywords:
- FinalizeableObjectQueued method [.NET Framework profiling]
- ICorProfilerCallback2::FinalizeableObjectQueued method [.NET Framework profiling]
ms.assetid: 92d76893-683c-475d-9996-5bff03cdb10f
topic_type:
- apiref
ms.openlocfilehash: b9093f920a8c14247bc51471da3682c7e500afa4
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865804"
---
# <a name="icorprofilercallback2finalizeableobjectqueued-method"></a><span data-ttu-id="4d1db-102">ICorProfilerCallback2::FinalizeableObjectQueued-Methode</span><span class="sxs-lookup"><span data-stu-id="4d1db-102">ICorProfilerCallback2::FinalizeableObjectQueued Method</span></span>
<span data-ttu-id="4d1db-103">Benachrichtigt den Codeprofiler, dass ein Objekt mit einem Finalizer für die Ausführung seiner `Finalize` Methode in die Warteschlange für den Finalizerthread eingereiht wurde.</span><span class="sxs-lookup"><span data-stu-id="4d1db-103">Notifies the code profiler that an object with a finalizer has been queued to the finalizer thread for execution of its `Finalize` method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d1db-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4d1db-104">Syntax</span></span>  
  
```cpp  
HRESULT FinalizeableObjectQueued(  
    [in] DWORD finalizerFlags,  
    [in] ObjectID objectID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d1db-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="4d1db-105">Parameters</span></span>  
 `finalizerFlags`  
 <span data-ttu-id="4d1db-106">in Ein Wert der [COR_PRF_FINALIZER_FLAGS](cor-prf-finalizer-flags-enumeration.md) Enumeration, der Aspekte des Finalizers beschreibt.</span><span class="sxs-lookup"><span data-stu-id="4d1db-106">[in] A value of the [COR_PRF_FINALIZER_FLAGS](cor-prf-finalizer-flags-enumeration.md) enumeration that describes aspects of the finalizer.</span></span>  
  
 `objectID`  
 <span data-ttu-id="4d1db-107">in Die ID des Objekts, das in die Warteschlange eingereiht wurde.</span><span class="sxs-lookup"><span data-stu-id="4d1db-107">[in] The ID of the object that has been queued.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d1db-108">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4d1db-108">Requirements</span></span>  
 <span data-ttu-id="4d1db-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d1db-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d1db-110">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4d1db-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4d1db-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d1db-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d1db-112">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d1db-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d1db-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d1db-113">See also</span></span>

- [<span data-ttu-id="4d1db-114">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4d1db-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="4d1db-115">ICorProfilerCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4d1db-115">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
