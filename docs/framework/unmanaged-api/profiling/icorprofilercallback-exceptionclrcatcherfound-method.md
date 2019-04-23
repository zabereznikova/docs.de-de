---
title: ICorProfilerCallback::ExceptionCLRCatcherFound-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 59225677671388b4ed31f7fa440b6e502b604c63
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59073013"
---
# <a name="icorprofilercallbackexceptionclrcatcherfound-method"></a><span data-ttu-id="dcb78-102">ICorProfilerCallback::ExceptionCLRCatcherFound-Methode</span><span class="sxs-lookup"><span data-stu-id="dcb78-102">ICorProfilerCallback::ExceptionCLRCatcherFound Method</span></span>
<span data-ttu-id="dcb78-103">Wird aufgerufen, wenn eine `catch` -Block für eine Ausnahme in der common Language Runtime (CLR) selbst gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="dcb78-103">Called when a `catch` block for an exception is found inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="dcb78-104">Diese Methode ist in .NET Framework, Version 2.0, veraltet.</span><span class="sxs-lookup"><span data-stu-id="dcb78-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcb78-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="dcb78-105">Syntax</span></span>  
  
```  
HRESULT ExceptionCLRCatcherFound();  
```  
  
## <a name="requirements"></a><span data-ttu-id="dcb78-106">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dcb78-106">Requirements</span></span>  
 <span data-ttu-id="dcb78-107">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dcb78-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcb78-108">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dcb78-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dcb78-109">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dcb78-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dcb78-110">**.NET Framework Version:** 1.0</span><span class="sxs-lookup"><span data-stu-id="dcb78-110">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcb78-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dcb78-111">See also</span></span>

- [<span data-ttu-id="dcb78-112">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dcb78-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="dcb78-113">ExceptionCLRCatcherExecute-Methode</span><span class="sxs-lookup"><span data-stu-id="dcb78-113">ExceptionCLRCatcherExecute Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherexecute-method.md)
