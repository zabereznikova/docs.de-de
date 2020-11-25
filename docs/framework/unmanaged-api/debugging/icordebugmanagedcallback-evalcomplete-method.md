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
ms.openlocfilehash: e95874447528989af68f5c97825691532195889f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731799"
---
# <a name="icordebugmanagedcallbackevalcomplete-method"></a><span data-ttu-id="029a3-102">ICorDebugManagedCallback::EvalComplete-Methode</span><span class="sxs-lookup"><span data-stu-id="029a3-102">ICorDebugManagedCallback::EvalComplete Method</span></span>

<span data-ttu-id="029a3-103">Benachrichtigt den Debugger, dass eine Auswertung abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="029a3-103">Notifies the debugger that an evaluation has been completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="029a3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="029a3-104">Syntax</span></span>  
  
```cpp  
HRESULT EvalComplete (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="029a3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="029a3-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="029a3-106">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, in der die Auswertung durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="029a3-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation was performed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="029a3-107">in Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, in dem die Auswertung durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="029a3-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation was performed.</span></span>  
  
 `pEval`  
 <span data-ttu-id="029a3-108">in Ein Zeiger auf ein ICorDebugEval-Objekt, das den Code darstellt, der die Auswertung durchgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="029a3-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="029a3-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="029a3-109">Requirements</span></span>  

 <span data-ttu-id="029a3-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="029a3-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="029a3-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="029a3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="029a3-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="029a3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="029a3-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="029a3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="029a3-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="029a3-114">See also</span></span>

- [<span data-ttu-id="029a3-115">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="029a3-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
