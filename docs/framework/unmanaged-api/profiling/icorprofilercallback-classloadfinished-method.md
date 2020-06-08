---
title: ICorProfilerCallback::ClassLoadFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadFinished
helpviewer_keywords:
- ClassLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ClassLoadFinished method [.NET Framework profiling]
ms.assetid: 3dd80fbe-d62d-4d4d-acf8-5b7d0efe607e
topic_type:
- apiref
ms.openlocfilehash: 4be2a50664b001e865b5ecdd9aabe8ba727b8c26
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500389"
---
# <a name="icorprofilercallbackclassloadfinished-method"></a><span data-ttu-id="bd5f4-102">ICorProfilerCallback::ClassLoadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="bd5f4-102">ICorProfilerCallback::ClassLoadFinished Method</span></span>
<span data-ttu-id="bd5f4-103">Benachrichtigt den Profiler, dass eine Klasse den Ladevorgang abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="bd5f4-103">Notifies the profiler that a class has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd5f4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bd5f4-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassLoadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd5f4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bd5f4-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="bd5f4-106">\[in] identifiziert die Klasse, die geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="bd5f4-106">\[in] Identifies the class that was loaded.</span></span>

- `hrStatus`

  <span data-ttu-id="bd5f4-107">\[in] ein HRESULT, das angibt, ob die Klasse erfolgreich geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="bd5f4-107">\[in] An HRESULT that indicates whether the class loaded successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="bd5f4-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="bd5f4-108">Remarks</span></span>  
 <span data-ttu-id="bd5f4-109">Der Wert von `classId` ist für eine Informationsanforderung erst gültig, wenn die- `ClassLoadFinished` Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="bd5f4-109">The value of `classId` is not valid for an information request until the `ClassLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="bd5f4-110">Einige Teile des Ladens der-Klasse können nach dem Rückruf fortgesetzt werden `ClassLoadFinished` .</span><span class="sxs-lookup"><span data-stu-id="bd5f4-110">Some parts of loading the class might continue after the `ClassLoadFinished` callback.</span></span> <span data-ttu-id="bd5f4-111">Ein Fehler HRESULT in `hrStatus` weist auf einen Fehler hin.</span><span class="sxs-lookup"><span data-stu-id="bd5f4-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="bd5f4-112">Ein HRESULT-Erfolg in `hrStatus` gibt jedoch nur an, dass der erste Teil des Ladens der Klasse erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="bd5f4-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd5f4-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bd5f4-113">Requirements</span></span>  
 <span data-ttu-id="bd5f4-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd5f4-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd5f4-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bd5f4-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bd5f4-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd5f4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd5f4-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd5f4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd5f4-118">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="bd5f4-118">See also</span></span>

- [<span data-ttu-id="bd5f4-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bd5f4-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="bd5f4-120">ClassLoadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="bd5f4-120">ClassLoadStarted Method</span></span>](icorprofilercallback-classloadstarted-method.md)
