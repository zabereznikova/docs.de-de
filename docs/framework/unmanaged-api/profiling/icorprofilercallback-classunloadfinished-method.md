---
title: ICorProfilerCallback::ClassUnloadFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadFinished
helpviewer_keywords:
- ICorProfilerCallback::ClassUnloadFinished method [.NET Framework profiling]
- ClassUnloadFinished method [.NET Framework profiling]
ms.assetid: 55674b68-678a-4747-ae06-4e91519c7305
topic_type:
- apiref
ms.openlocfilehash: 14eb90c707618796d6d62ed2ec5710ceba31ba6c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500376"
---
# <a name="icorprofilercallbackclassunloadfinished-method"></a><span data-ttu-id="ff43f-102">ICorProfilerCallback::ClassUnloadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="ff43f-102">ICorProfilerCallback::ClassUnloadFinished Method</span></span>
<span data-ttu-id="ff43f-103">Benachrichtigt den Profiler, dass eine Klasse das entladen abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="ff43f-103">Notifies the profiler that a class has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff43f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ff43f-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassUnloadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff43f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ff43f-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="ff43f-106">\[in] identifiziert die Klasse, die entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="ff43f-106">\[in] Identifies the class that was unloaded.</span></span>

- `hrStatus`

  <span data-ttu-id="ff43f-107">\[in] ein HRESULT, das angibt, ob die Klasse erfolgreich entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="ff43f-107">\[in] An HRESULT that indicates whether the class was unloaded successfully.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="ff43f-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ff43f-108">Remarks</span></span>  
 <span data-ttu-id="ff43f-109">Einige Teile des Entladen der Klasse können nach dem Rückruf fortgesetzt werden `ClassUnloadFinished` .</span><span class="sxs-lookup"><span data-stu-id="ff43f-109">Some parts of unloading the class might continue after the `ClassUnloadFinished` callback.</span></span> <span data-ttu-id="ff43f-110">Ein Fehler HRESULT in `hrStatus` weist auf einen Fehler hin.</span><span class="sxs-lookup"><span data-stu-id="ff43f-110">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="ff43f-111">Ein HRESULT-Erfolg in `hrStatus` gibt jedoch nur an, dass der erste Teil des Entladens der Klasse erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="ff43f-111">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff43f-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ff43f-112">Requirements</span></span>  
 <span data-ttu-id="ff43f-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff43f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff43f-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ff43f-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ff43f-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff43f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff43f-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff43f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff43f-117">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="ff43f-117">See also</span></span>

- [<span data-ttu-id="ff43f-118">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ff43f-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="ff43f-119">ClassUnloadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="ff43f-119">ClassUnloadStarted Method</span></span>](icorprofilercallback-classunloadstarted-method.md)
