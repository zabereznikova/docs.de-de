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
ms.openlocfilehash: 20a841006d51671a491e11c4e40287baf739d191
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209824"
---
# <a name="icordebugmanagedcallbackevalexception-method"></a><span data-ttu-id="d8eb3-102">ICorDebugManagedCallback::EvalException-Methode</span><span class="sxs-lookup"><span data-stu-id="d8eb3-102">ICorDebugManagedCallback::EvalException Method</span></span>
<span data-ttu-id="d8eb3-103">Benachrichtigt den Debugger, dass eine Auswertung mit einer nicht behandelten Ausnahme beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="d8eb3-103">Notifies the debugger that an evaluation has terminated with an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8eb3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d8eb3-104">Syntax</span></span>  
  
```cpp  
HRESULT EvalException (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8eb3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d8eb3-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="d8eb3-106">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, in der die Auswertung beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="d8eb3-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation terminated.</span></span>  
  
 `pThread`  
 <span data-ttu-id="d8eb3-107">in Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, in dem die Auswertung beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="d8eb3-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation terminated.</span></span>  
  
 `pEval`  
 <span data-ttu-id="d8eb3-108">in Ein Zeiger auf ein ICorDebugEval-Objekt, das den Code darstellt, der die Auswertung durchgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="d8eb3-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8eb3-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d8eb3-109">Requirements</span></span>  
 <span data-ttu-id="d8eb3-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8eb3-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8eb3-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d8eb3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d8eb3-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8eb3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8eb3-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8eb3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8eb3-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8eb3-114">See also</span></span>

- [<span data-ttu-id="d8eb3-115">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d8eb3-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
