---
title: ICorProfilerCallback::ExceptionSearchFilterLeave-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFilterLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFilterLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionSearchFilterLeave method [.NET Framework profiling]
- ExceptionSearchFilterLeave method [.NET Framework profiling]
ms.assetid: c28a2a82-dd11-4385-843f-b509fb61753b
topic_type:
- apiref
ms.openlocfilehash: fbece20701fbde5551e025b4f116f9873abf444d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500207"
---
# <a name="icorprofilercallbackexceptionsearchfilterleave-method"></a><span data-ttu-id="c1057-102">ICorProfilerCallback::ExceptionSearchFilterLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="c1057-102">ICorProfilerCallback::ExceptionSearchFilterLeave Method</span></span>
<span data-ttu-id="c1057-103">Benachrichtigt den Profiler, dass die Ausführung eines Benutzer Filters soeben abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="c1057-103">Notifies the profiler that a user filter has just finished executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1057-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c1057-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFilterLeave();  
```  
  
## <a name="requirements"></a><span data-ttu-id="c1057-105">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c1057-105">Requirements</span></span>  
 <span data-ttu-id="c1057-106">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1057-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1057-107">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c1057-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c1057-108">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1057-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1057-109">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1057-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1057-110">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="c1057-110">See also</span></span>

- [<span data-ttu-id="c1057-111">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1057-111">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="c1057-112">ExceptionSearchFilterEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="c1057-112">ExceptionSearchFilterEnter Method</span></span>](icorprofilercallback-exceptionsearchfilterenter-method.md)
