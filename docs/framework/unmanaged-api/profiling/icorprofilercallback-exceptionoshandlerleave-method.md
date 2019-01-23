---
title: ICorProfilerCallback::ExceptionOSHandlerLeave-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionOSHandlerLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionOSHandlerLeave
helpviewer_keywords:
- ExceptionOSHandlerLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionOSHandlerLeave method [.NET Framework profiling]
ms.assetid: 4d164676-0ee9-4f67-a8ea-cb474db09053
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7c8339142ef382ca029e9dd32c0270bd794ffcc2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54546688"
---
# <a name="icorprofilercallbackexceptionoshandlerleave-method"></a><span data-ttu-id="42efb-102">ICorProfilerCallback::ExceptionOSHandlerLeave-Methode</span><span class="sxs-lookup"><span data-stu-id="42efb-102">ICorProfilerCallback::ExceptionOSHandlerLeave Method</span></span>
<span data-ttu-id="42efb-103">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="42efb-103">Not implemented.</span></span> <span data-ttu-id="42efb-104">Ein Profiler, der nicht verwaltete Ausnahmeinformationen benötigt, muss diese Informationen mithilfe anderer Methoden abrufen.</span><span class="sxs-lookup"><span data-stu-id="42efb-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42efb-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="42efb-105">Syntax</span></span>  
  
```  
HRESULT ExceptionOSHandlerLeave(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="42efb-106">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="42efb-106">Requirements</span></span>  
 <span data-ttu-id="42efb-107">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42efb-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42efb-108">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="42efb-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="42efb-109">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42efb-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42efb-110">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42efb-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42efb-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42efb-111">See also</span></span>
- [<span data-ttu-id="42efb-112">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="42efb-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
