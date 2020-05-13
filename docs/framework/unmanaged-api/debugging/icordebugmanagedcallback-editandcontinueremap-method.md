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
ms.openlocfilehash: 78b87b5c566b0d760a205757430123665fb2fcd3
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213711"
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="67c93-102">ICorDebugManagedCallback::EditAndContinueRemap-Methode</span><span class="sxs-lookup"><span data-stu-id="67c93-102">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>
<span data-ttu-id="67c93-103">Diese Methode ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="67c93-103">This method has been deprecated.</span></span> <span data-ttu-id="67c93-104">Der Debugger wird benachrichtigt, dass ein Umwandlungs-Ereignis an die integrierte Entwicklungsumgebung (Integrated Development Environment, IDE) gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="67c93-104">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67c93-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="67c93-105">Syntax</span></span>  
  
```cpp  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="67c93-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="67c93-106">Remarks</span></span>  
 <span data-ttu-id="67c93-107">Die- `EditAndContinueRemap` Methode wird aufgerufen, wenn versucht wurde, den Code in einer alten Version einer aktualisierten Funktion auszuführen.</span><span class="sxs-lookup"><span data-stu-id="67c93-107">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="67c93-108">Der Common Language Runtime ruft die- `EditAndContinueRemap` Methode auf, um ein Umwandlungs-Ereignis an die IDE zu senden.</span><span class="sxs-lookup"><span data-stu-id="67c93-108">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67c93-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="67c93-109">Requirements</span></span>  
 <span data-ttu-id="67c93-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67c93-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67c93-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67c93-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67c93-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67c93-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67c93-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67c93-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67c93-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67c93-114">See also</span></span>

- [<span data-ttu-id="67c93-115">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="67c93-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
