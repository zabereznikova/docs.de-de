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
ms.openlocfilehash: 9cb956c0262fdcdb5971d049ea7b057aa4d952c0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781909"
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="bc578-102">ICorDebugManagedCallback::EditAndContinueRemap-Methode</span><span class="sxs-lookup"><span data-stu-id="bc578-102">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>
<span data-ttu-id="bc578-103">Diese Methode ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="bc578-103">This method has been deprecated.</span></span> <span data-ttu-id="bc578-104">Der Debugger wird benachrichtigt, dass ein Umwandlungs-Ereignis an die integrierte Entwicklungsumgebung (Integrated Development Environment, IDE) gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="bc578-104">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc578-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="bc578-105">Syntax</span></span>  
  
```cpp  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="bc578-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bc578-106">Remarks</span></span>  
 <span data-ttu-id="bc578-107">Die `EditAndContinueRemap`-Methode wird aufgerufen, wenn versucht wurde, den Code in einer alten Version einer aktualisierten Funktion auszuführen.</span><span class="sxs-lookup"><span data-stu-id="bc578-107">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="bc578-108">Der Common Language Runtime ruft die `EditAndContinueRemap`-Methode auf, um ein Umwandlungs-Ereignis an die IDE zu senden.</span><span class="sxs-lookup"><span data-stu-id="bc578-108">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc578-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bc578-109">Requirements</span></span>  
 <span data-ttu-id="bc578-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc578-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc578-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bc578-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bc578-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc578-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc578-113">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc578-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc578-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc578-114">See also</span></span>

- [<span data-ttu-id="bc578-115">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bc578-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
