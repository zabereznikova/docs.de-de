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
ms.openlocfilehash: 0431b54997c9889e2b3206392e86e4dcde45ffb3
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212450"
---
# <a name="icordebugmanagedcallbackevalcomplete-method"></a><span data-ttu-id="ae938-102">ICorDebugManagedCallback::EvalComplete-Methode</span><span class="sxs-lookup"><span data-stu-id="ae938-102">ICorDebugManagedCallback::EvalComplete Method</span></span>
<span data-ttu-id="ae938-103">Benachrichtigt den Debugger, dass eine Auswertung abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="ae938-103">Notifies the debugger that an evaluation has been completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae938-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ae938-104">Syntax</span></span>  
  
```cpp  
HRESULT EvalComplete (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae938-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ae938-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="ae938-106">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, in der die Auswertung durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="ae938-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation was performed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="ae938-107">in Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, in dem die Auswertung durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="ae938-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation was performed.</span></span>  
  
 `pEval`  
 <span data-ttu-id="ae938-108">in Ein Zeiger auf ein ICorDebugEval-Objekt, das den Code darstellt, der die Auswertung durchgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="ae938-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae938-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ae938-109">Requirements</span></span>  
 <span data-ttu-id="ae938-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae938-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae938-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae938-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae938-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae938-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae938-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae938-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae938-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae938-114">See also</span></span>

- [<span data-ttu-id="ae938-115">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ae938-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
