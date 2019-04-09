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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cab4b039d225f4ee1b00add6ffec63fd35be8857
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59202806"
---
# <a name="icorprofilercallbackclassloadfinished-method"></a><span data-ttu-id="a7bda-102">ICorProfilerCallback::ClassLoadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="a7bda-102">ICorProfilerCallback::ClassLoadFinished Method</span></span>
<span data-ttu-id="a7bda-103">Benachrichtigt den Profiler, dass eine Klasse vollständig geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="a7bda-103">Notifies the profiler that a class has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7bda-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a7bda-104">Syntax</span></span>  
  
```  
HRESULT ClassLoadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7bda-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a7bda-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="a7bda-106">[in] Identifiziert die Klasse, die geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="a7bda-106">[in] Identifies the class that was loaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="a7bda-107">[in] Ein HRESULT, der angibt, ob die Klasse wurde erfolgreich geladen.</span><span class="sxs-lookup"><span data-stu-id="a7bda-107">[in] An HRESULT that indicates whether the class loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7bda-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a7bda-108">Remarks</span></span>  
 <span data-ttu-id="a7bda-109">Der Wert des `classId` gilt nicht für eine Anforderung von Informationen bis der `ClassLoadFinished` Methode wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="a7bda-109">The value of `classId` is not valid for an information request until the `ClassLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="a7bda-110">Laden Sie die Klasse möglicherweise weiterhin nach den `ClassLoadFinished` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="a7bda-110">Some parts of loading the class might continue after the `ClassLoadFinished` callback.</span></span> <span data-ttu-id="a7bda-111">Fehler-HRESULT in `hrStatus` gibt einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="a7bda-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="a7bda-112">Allerdings einen HRESULT-Erfolg in `hrStatus` gibt nur an, dass der erste Teil, das Laden der Klasse erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="a7bda-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the class has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7bda-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a7bda-113">Requirements</span></span>  
 <span data-ttu-id="a7bda-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7bda-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7bda-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a7bda-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a7bda-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7bda-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a7bda-117">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="a7bda-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a7bda-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7bda-118">See also</span></span>

- [<span data-ttu-id="a7bda-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a7bda-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="a7bda-120">ClassLoadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="a7bda-120">ClassLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)
