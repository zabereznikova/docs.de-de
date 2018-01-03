---
title: ICorDebugManagedCallback::EditAndContinueRemap-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.EditAndContinueRemap
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::EditAndContinueRemap
helpviewer_keywords:
- EditAndContinueRemap method [.NET Framework debugging]
- ICorDebugManagedCallback::EditAndContinueRemap method [.NET Framework debugging]
ms.assetid: 24a8fcce-317e-48ff-aefc-d86123ada935
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 90c22b697677ec493b8093117af0a9d1a86268ea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="8ee15-102">ICorDebugManagedCallback::EditAndContinueRemap-Methode</span><span class="sxs-lookup"><span data-stu-id="8ee15-102">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>
<span data-ttu-id="8ee15-103">Diese Methode ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="8ee15-103">This method has been deprecated.</span></span> <span data-ttu-id="8ee15-104">Dem Debugger benachrichtigt, dass ein Neuzuordnungsereignis an der integrierten Entwicklungsumgebung (IDE) gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="8ee15-104">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ee15-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8ee15-105">Syntax</span></span>  
  
```  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="8ee15-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8ee15-106">Remarks</span></span>  
 <span data-ttu-id="8ee15-107">Die `EditAndContinueRemap` Methode wird aufgerufen, wenn die Ausführung des Codes in einer alten Version einer aktualisierten Funktion versucht wurde.</span><span class="sxs-lookup"><span data-stu-id="8ee15-107">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="8ee15-108">Die common Language Runtime Ruft die `EditAndContinueRemap` Methode, um ein Neuzuordnungsereignis der IDE zu senden.</span><span class="sxs-lookup"><span data-stu-id="8ee15-108">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ee15-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8ee15-109">Requirements</span></span>  
 <span data-ttu-id="8ee15-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ee15-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ee15-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8ee15-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8ee15-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8ee15-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8ee15-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ee15-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ee15-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ee15-114">See Also</span></span>  
 [<span data-ttu-id="8ee15-115">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8ee15-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
