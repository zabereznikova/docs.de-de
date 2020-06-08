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
ms.openlocfilehash: 4f4d53b086453adce38902518f2de3dde1f2812f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500246"
---
# <a name="icorprofilercallbackexceptionclrcatcherfound-method"></a><span data-ttu-id="285a4-102">ICorProfilerCallback::ExceptionCLRCatcherFound-Methode</span><span class="sxs-lookup"><span data-stu-id="285a4-102">ICorProfilerCallback::ExceptionCLRCatcherFound Method</span></span>
<span data-ttu-id="285a4-103">Wird aufgerufen, wenn ein `catch` Block für eine Ausnahme innerhalb der Common Language Runtime (CLR) selbst gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="285a4-103">Called when a `catch` block for an exception is found inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="285a4-104">Diese Methode ist in der .NET Framework Version 2,0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="285a4-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="285a4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="285a4-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherFound();  
```  
  
## <a name="requirements"></a><span data-ttu-id="285a4-106">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="285a4-106">Requirements</span></span>  
 <span data-ttu-id="285a4-107">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="285a4-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="285a4-108">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="285a4-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="285a4-109">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="285a4-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="285a4-110">**.NET Framework Version:** 1,0</span><span class="sxs-lookup"><span data-stu-id="285a4-110">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="285a4-111">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="285a4-111">See also</span></span>

- [<span data-ttu-id="285a4-112">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="285a4-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="285a4-113">ExceptionCLRCatcherExecute-Methode</span><span class="sxs-lookup"><span data-stu-id="285a4-113">ExceptionCLRCatcherExecute Method</span></span>](icorprofilercallback-exceptionclrcatcherexecute-method.md)
