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
ms.openlocfilehash: e1e97b8df2ad81f91cd7250afbe4c5cc544ca6be
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54702248"
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="2d114-102">ICorDebugManagedCallback::EditAndContinueRemap-Methode</span><span class="sxs-lookup"><span data-stu-id="2d114-102">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>
<span data-ttu-id="2d114-103">Diese Methode ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="2d114-103">This method has been deprecated.</span></span> <span data-ttu-id="2d114-104">Dem Debugger benachrichtigt, dass die integrierte Entwicklungsumgebung (IDE) eine Neuzuordnungsereignis gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="2d114-104">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d114-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d114-105">Syntax</span></span>  
  
```  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="2d114-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2d114-106">Remarks</span></span>  
 <span data-ttu-id="2d114-107">Die `EditAndContinueRemap` Methode wird aufgerufen, wenn die Ausführung des Codes in einer alten Version einer aktualisierten Funktion versucht wurde.</span><span class="sxs-lookup"><span data-stu-id="2d114-107">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="2d114-108">Die common Language Runtime Ruft die `EditAndContinueRemap` Methode, um eine Neuzuordnungsereignis an die IDE zu senden.</span><span class="sxs-lookup"><span data-stu-id="2d114-108">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d114-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2d114-109">Requirements</span></span>  
 <span data-ttu-id="2d114-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d114-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d114-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2d114-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2d114-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d114-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d114-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d114-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d114-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d114-114">See also</span></span>
- [<span data-ttu-id="2d114-115">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2d114-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
