---
title: ICorProfilerCallback::ExceptionCLRCatcherExecute-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCLRCatcherExecute
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherExecute
helpviewer_keywords:
- ExceptionCLRCatcherExecute method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionCLRCatcherExecute method [.NET Framework profiling]
ms.assetid: aaac8f98-5cf4-42c7-b04b-556cce367e36
topic_type:
- apiref
ms.openlocfilehash: f14dff33217656c35379a214f007ccb3642ef4b1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866454"
---
# <a name="icorprofilercallbackexceptionclrcatcherexecute-method"></a><span data-ttu-id="8d627-102">ICorProfilerCallback::ExceptionCLRCatcherExecute-Methode</span><span class="sxs-lookup"><span data-stu-id="8d627-102">ICorProfilerCallback::ExceptionCLRCatcherExecute Method</span></span>
<span data-ttu-id="8d627-103">Wird aufgerufen, wenn ein `catch`-Block für eine Ausnahme innerhalb der Common Language Runtime (CLR) selbst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8d627-103">Called when a `catch` block for an exception is executed inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="8d627-104">Diese Methode ist in der .NET Framework Version 2,0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="8d627-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d627-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8d627-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherExecute();  
```  
  
## <a name="requirements"></a><span data-ttu-id="8d627-106">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8d627-106">Requirements</span></span>  
 <span data-ttu-id="8d627-107">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d627-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d627-108">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8d627-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8d627-109">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d627-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d627-110">**.NET Framework Versionen:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="8d627-110">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d627-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8d627-111">See also</span></span>

- [<span data-ttu-id="8d627-112">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8d627-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="8d627-113">ExceptionCLRCatcherFound-Methode</span><span class="sxs-lookup"><span data-stu-id="8d627-113">ExceptionCLRCatcherFound Method</span></span>](icorprofilercallback-exceptionclrcatcherfound-method.md)
