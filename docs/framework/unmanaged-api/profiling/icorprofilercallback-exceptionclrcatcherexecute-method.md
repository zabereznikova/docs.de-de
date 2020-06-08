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
ms.openlocfilehash: b79c8dd9f27805e00535dde53c6ee9f5ee457b42
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500262"
---
# <a name="icorprofilercallbackexceptionclrcatcherexecute-method"></a><span data-ttu-id="73281-102">ICorProfilerCallback::ExceptionCLRCatcherExecute-Methode</span><span class="sxs-lookup"><span data-stu-id="73281-102">ICorProfilerCallback::ExceptionCLRCatcherExecute Method</span></span>
<span data-ttu-id="73281-103">Wird aufgerufen, wenn ein `catch` Block für eine Ausnahme innerhalb der Common Language Runtime (CLR) selbst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="73281-103">Called when a `catch` block for an exception is executed inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="73281-104">Diese Methode ist in der .NET Framework Version 2,0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="73281-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73281-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="73281-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherExecute();  
```  
  
## <a name="requirements"></a><span data-ttu-id="73281-106">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="73281-106">Requirements</span></span>  
 <span data-ttu-id="73281-107">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73281-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73281-108">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="73281-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="73281-109">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73281-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73281-110">**.NET Framework Versionen:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="73281-110">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73281-111">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="73281-111">See also</span></span>

- [<span data-ttu-id="73281-112">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="73281-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="73281-113">ExceptionCLRCatcherFound-Methode</span><span class="sxs-lookup"><span data-stu-id="73281-113">ExceptionCLRCatcherFound Method</span></span>](icorprofilercallback-exceptionclrcatcherfound-method.md)
