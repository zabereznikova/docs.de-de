---
title: ICorProfilerCallback::ExceptionOSHandlerEnter-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionOSHandlerEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionOSHandlerEnter
helpviewer_keywords:
- ExceptionOSHandlerEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionOSHandlerEnter method [.NET Framework profiling]
ms.assetid: 09238b9b-9359-4780-89dc-2f5e4f57920e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1fcdd52e648b2461036921772b6b5684ba6aec22
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598146"
---
# <a name="icorprofilercallbackexceptionoshandlerenter-method"></a><span data-ttu-id="9e662-102">ICorProfilerCallback::ExceptionOSHandlerEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="9e662-102">ICorProfilerCallback::ExceptionOSHandlerEnter Method</span></span>
<span data-ttu-id="9e662-103">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="9e662-103">Not implemented.</span></span> <span data-ttu-id="9e662-104">Ein Profiler, der nicht verwaltete Ausnahmeinformationen benötigt, muss diese Informationen mithilfe anderer Methoden abrufen.</span><span class="sxs-lookup"><span data-stu-id="9e662-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e662-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9e662-105">Syntax</span></span>  
  
```  
HRESULT ExceptionOSHandlerEnter(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="9e662-106">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9e662-106">Requirements</span></span>  
 <span data-ttu-id="9e662-107">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e662-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e662-108">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9e662-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9e662-109">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e662-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e662-110">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e662-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e662-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e662-111">See also</span></span>

- [<span data-ttu-id="9e662-112">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9e662-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
