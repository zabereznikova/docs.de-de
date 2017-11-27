---
title: ICorProfilerCallback::ExceptionSearchFunctionLeave-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionSearchFunctionLeave
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionSearchFunctionLeave
helpviewer_keywords:
- ExceptionSearchFunctionLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFunctionLeave method [.NET Framework profiling]
ms.assetid: 01de7ac6-0aad-42ef-bf93-50737667b0a4
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 063b8e666b122103c6776b86aa86d1215e200016
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackexceptionsearchfunctionleave-method"></a><span data-ttu-id="c8100-102">ICorProfilerCallback::ExceptionSearchFunctionLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="c8100-102">ICorProfilerCallback::ExceptionSearchFunctionLeave Method</span></span>
<span data-ttu-id="c8100-103">Benachrichtigt den Profiler, dass die Suchphase der Ausnahmebehandlung Suche in einer Funktion abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="c8100-103">Notifies the profiler that the search phase of exception handling has finished searching a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8100-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c8100-104">Syntax</span></span>  
  
```  
HRESULT ExceptionSearchFunctionLeave();  
```  
  
## <a name="requirements"></a><span data-ttu-id="c8100-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c8100-105">Requirements</span></span>  
 <span data-ttu-id="c8100-106">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8100-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8100-107">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c8100-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c8100-108">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8100-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8100-109">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8100-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8100-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8100-110">See Also</span></span>  
 [<span data-ttu-id="c8100-111">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c8100-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="c8100-112">ExceptionSearchFunctionEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="c8100-112">ExceptionSearchFunctionEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md)
