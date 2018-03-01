---
title: ICorProfilerCallback::ExceptionCLRCatcherFound-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback.ExceptionCLRCatcherFound
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherFound
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherFound method [.NET Framework profiling]
- ExceptionCLRCatcherFound method [.NET Framework profiling]
ms.assetid: 73fe8b4b-8f9a-4ba5-a10c-b26521396a66
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5f539a93b72c7bf3570dd3cf4cb484564999699c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackexceptionclrcatcherfound-method"></a><span data-ttu-id="0efa7-102">ICorProfilerCallback::ExceptionCLRCatcherFound-Methode</span><span class="sxs-lookup"><span data-stu-id="0efa7-102">ICorProfilerCallback::ExceptionCLRCatcherFound Method</span></span>
<span data-ttu-id="0efa7-103">Wird aufgerufen, wenn eine `catch` -Block für eine Ausnahme in der common Language Runtime (CLR) selbst gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="0efa7-103">Called when a `catch` block for an exception is found inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="0efa7-104">Diese Methode ist veraltet in .NET Framework, Version 2.0.</span><span class="sxs-lookup"><span data-stu-id="0efa7-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0efa7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0efa7-105">Syntax</span></span>  
  
```  
HRESULT ExceptionCLRCatcherFound();  
```  
  
## <a name="requirements"></a><span data-ttu-id="0efa7-106">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0efa7-106">Requirements</span></span>  
 <span data-ttu-id="0efa7-107">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0efa7-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0efa7-108">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0efa7-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0efa7-109">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0efa7-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0efa7-110">**.NET Framework-Version:** 1.0</span><span class="sxs-lookup"><span data-stu-id="0efa7-110">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0efa7-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0efa7-111">See Also</span></span>  
 [<span data-ttu-id="0efa7-112">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0efa7-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="0efa7-113">ExceptionCLRCatcherExecute-Methode</span><span class="sxs-lookup"><span data-stu-id="0efa7-113">ExceptionCLRCatcherExecute Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherexecute-method.md)
