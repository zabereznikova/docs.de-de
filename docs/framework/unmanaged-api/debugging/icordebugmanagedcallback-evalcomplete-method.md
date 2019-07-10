---
title: ICorDebugManagedCallback::EvalComplete-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EvalComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EvalComplete
helpviewer_keywords:
- ICorDebugManagedCallback::EvalComplete method [.NET Framework debugging]
- EvalComplete method [.NET Framework debugging]
ms.assetid: f74ab4eb-cd1b-407c-a66d-8ec0d85647f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a874646a6746a9b2fc8ce597e6c1ca47340c199a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759649"
---
# <a name="icordebugmanagedcallbackevalcomplete-method"></a><span data-ttu-id="e250e-102">ICorDebugManagedCallback::EvalComplete-Methode</span><span class="sxs-lookup"><span data-stu-id="e250e-102">ICorDebugManagedCallback::EvalComplete Method</span></span>
<span data-ttu-id="e250e-103">Benachrichtigt den Debugger an, dass eine Auswertung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="e250e-103">Notifies the debugger that an evaluation has been completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e250e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e250e-104">Syntax</span></span>  
  
```cpp  
HRESULT EvalComplete (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e250e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e250e-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="e250e-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, in der die Auswertung ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="e250e-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation was performed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="e250e-107">[in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, in dem die Evaluierung ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="e250e-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation was performed.</span></span>  
  
 `pEval`  
 <span data-ttu-id="e250e-108">[in] Ein Zeiger auf ein ICorDebugEval-Objekt, das den Code darstellt, der die Auswertung ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e250e-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e250e-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e250e-109">Requirements</span></span>  
 <span data-ttu-id="e250e-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e250e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e250e-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e250e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e250e-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e250e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e250e-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e250e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e250e-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e250e-114">See also</span></span>

- [<span data-ttu-id="e250e-115">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e250e-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
