---
title: ICorDebugManagedCallback::EvalException-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EvalException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EvalException
helpviewer_keywords:
- EvalException method [.NET Framework debugging]
- ICorDebugManagedCallback::EvalException method [.NET Framework debugging]
ms.assetid: d6036345-18a3-45c1-a302-b1c6f2dced9b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4414bab535b63f55a580e93cc6de9cb0dedc073c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmanagedcallbackevalexception-method"></a><span data-ttu-id="e96da-102">ICorDebugManagedCallback::EvalException-Methode</span><span class="sxs-lookup"><span data-stu-id="e96da-102">ICorDebugManagedCallback::EvalException Method</span></span>
<span data-ttu-id="e96da-103">Benachrichtigt den Debugger, dass eine Auswertung mit einer nicht behandelten Ausnahme beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e96da-103">Notifies the debugger that an evaluation has terminated with an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e96da-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e96da-104">Syntax</span></span>  
  
```  
HRESULT EvalException (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e96da-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e96da-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="e96da-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, in dem die Auswertung beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e96da-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation terminated.</span></span>  
  
 `pThread`  
 <span data-ttu-id="e96da-107">[in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, in dem die Auswertung beendet.</span><span class="sxs-lookup"><span data-stu-id="e96da-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation terminated.</span></span>  
  
 `pEval`  
 <span data-ttu-id="e96da-108">[in] Ein Zeiger auf ein ICorDebugEval-Objekt, das den Code darstellt, der die Auswertung ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e96da-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e96da-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e96da-109">Requirements</span></span>  
 <span data-ttu-id="e96da-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e96da-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e96da-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e96da-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e96da-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e96da-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e96da-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e96da-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e96da-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e96da-114">See Also</span></span>  
 [<span data-ttu-id="e96da-115">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e96da-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
