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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b640a6dee9ae50278d6a844d20d21eae156e9dd7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598545"
---
# <a name="icorprofilercallbackexceptionclrcatcherexecute-method"></a><span data-ttu-id="765d8-102">ICorProfilerCallback::ExceptionCLRCatcherExecute-Methode</span><span class="sxs-lookup"><span data-stu-id="765d8-102">ICorProfilerCallback::ExceptionCLRCatcherExecute Method</span></span>
<span data-ttu-id="765d8-103">Wird aufgerufen, wenn eine `catch` -Block für eine Ausnahme in der common Language Runtime (CLR) selbst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="765d8-103">Called when a `catch` block for an exception is executed inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="765d8-104">Diese Methode ist in .NET Framework, Version 2.0, veraltet.</span><span class="sxs-lookup"><span data-stu-id="765d8-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="765d8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="765d8-105">Syntax</span></span>  
  
```  
HRESULT ExceptionCLRCatcherExecute();  
```  
  
## <a name="requirements"></a><span data-ttu-id="765d8-106">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="765d8-106">Requirements</span></span>  
 <span data-ttu-id="765d8-107">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="765d8-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="765d8-108">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="765d8-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="765d8-109">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="765d8-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="765d8-110">**.NET Framework-Versionen:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="765d8-110">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="765d8-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="765d8-111">See also</span></span>

- [<span data-ttu-id="765d8-112">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="765d8-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="765d8-113">ExceptionCLRCatcherFound-Methode</span><span class="sxs-lookup"><span data-stu-id="765d8-113">ExceptionCLRCatcherFound Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherfound-method.md)
