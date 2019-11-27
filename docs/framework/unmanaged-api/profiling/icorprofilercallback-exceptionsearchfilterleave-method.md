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
ms.openlocfilehash: 70573164baf6839b5ae701c645526e8b1507ad35
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445353"
---
# <a name="icorprofilercallbackexceptionsearchfilterleave-method"></a><span data-ttu-id="f83db-102">ICorProfilerCallback::ExceptionSearchFilterLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="f83db-102">ICorProfilerCallback::ExceptionSearchFilterLeave Method</span></span>
<span data-ttu-id="f83db-103">Benachrichtigt den Profiler, dass die Ausführung eines Benutzer Filters soeben abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="f83db-103">Notifies the profiler that a user filter has just finished executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f83db-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f83db-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFilterLeave();  
```  
  
## <a name="requirements"></a><span data-ttu-id="f83db-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="f83db-105">Requirements</span></span>  
 <span data-ttu-id="f83db-106">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f83db-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f83db-107">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f83db-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f83db-108">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f83db-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f83db-109">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f83db-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f83db-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f83db-110">See also</span></span>

- [<span data-ttu-id="f83db-111">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f83db-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="f83db-112">ExceptionSearchFilterEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="f83db-112">ExceptionSearchFilterEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)
