---
title: ICorDebugManagedCallback::EditAndContinueRemap-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EditAndContinueRemap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EditAndContinueRemap
helpviewer_keywords:
- EditAndContinueRemap method [.NET Framework debugging]
- ICorDebugManagedCallback::EditAndContinueRemap method [.NET Framework debugging]
ms.assetid: 24a8fcce-317e-48ff-aefc-d86123ada935
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d1bdb14e8c3a61a2b94cef778660eeb5c85c34df
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59149772"
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="1c5af-102">ICorDebugManagedCallback::EditAndContinueRemap-Methode</span><span class="sxs-lookup"><span data-stu-id="1c5af-102">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>
<span data-ttu-id="1c5af-103">Diese Methode ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="1c5af-103">This method has been deprecated.</span></span> <span data-ttu-id="1c5af-104">Dem Debugger benachrichtigt, dass die integrierte Entwicklungsumgebung (IDE) eine Neuzuordnungsereignis gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="1c5af-104">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c5af-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1c5af-105">Syntax</span></span>  
  
```  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="1c5af-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1c5af-106">Remarks</span></span>  
 <span data-ttu-id="1c5af-107">Die `EditAndContinueRemap` Methode wird aufgerufen, wenn die Ausführung des Codes in einer alten Version einer aktualisierten Funktion versucht wurde.</span><span class="sxs-lookup"><span data-stu-id="1c5af-107">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="1c5af-108">Die common Language Runtime Ruft die `EditAndContinueRemap` Methode, um eine Neuzuordnungsereignis an die IDE zu senden.</span><span class="sxs-lookup"><span data-stu-id="1c5af-108">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c5af-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1c5af-109">Requirements</span></span>  
 <span data-ttu-id="1c5af-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c5af-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c5af-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c5af-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c5af-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c5af-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c5af-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c5af-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c5af-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c5af-114">See also</span></span>

- [<span data-ttu-id="1c5af-115">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1c5af-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
