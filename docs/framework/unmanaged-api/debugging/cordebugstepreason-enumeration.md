---
title: CorDebugStepReason-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugStepReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugStepReason
helpviewer_keywords:
- CorDebugStepReason enumeration [.NET Framework debugging]
ms.assetid: fe248069-b33c-48e1-a777-06ac9b239c54
topic_type:
- apiref
ms.openlocfilehash: 92aee981aca3bac32c0ef264799e486315ca5103
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789257"
---
# <a name="cordebugstepreason-enumeration"></a><span data-ttu-id="505b3-102">CorDebugStepReason-Enumeration</span><span class="sxs-lookup"><span data-stu-id="505b3-102">CorDebugStepReason Enumeration</span></span>
<span data-ttu-id="505b3-103">Gibt das Ergebnis eines einzelnen Schritts an.</span><span class="sxs-lookup"><span data-stu-id="505b3-103">Indicates the outcome of an individual step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="505b3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="505b3-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugStepReason {  
    STEP_NORMAL,  
    STEP_RETURN,  
    STEP_CALL,  
    STEP_EXCEPTION_FILTER,  
    STEP_EXCEPTION_HANDLER,  
    STEP_INTERCEPT,  
    STEP_EXIT  
} CorDebugStepReason;  
```  
  
## <a name="members"></a><span data-ttu-id="505b3-105">Member</span><span class="sxs-lookup"><span data-stu-id="505b3-105">Members</span></span>  
  
|<span data-ttu-id="505b3-106">Member</span><span class="sxs-lookup"><span data-stu-id="505b3-106">Member</span></span>|<span data-ttu-id="505b3-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="505b3-107">Description</span></span>|  
|------------|-----------------|  
|`STEP_NORMAL`|<span data-ttu-id="505b3-108">Die schrittweise Ausführung erfolgt in derselben Funktion.</span><span class="sxs-lookup"><span data-stu-id="505b3-108">Stepping completed normally, within the same function.</span></span>|  
|`STEP_RETURN`|<span data-ttu-id="505b3-109">Die schrittweise Ausführung wird nach der Rückgabe der Funktion fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="505b3-109">Stepping continued normally, after the function returned.</span></span>|  
|`STEP_CALL`|<span data-ttu-id="505b3-110">Schrittweise Fortsetzung am Anfang einer neu aufgerufenen Funktion.</span><span class="sxs-lookup"><span data-stu-id="505b3-110">Stepping continued normally, at the beginning of a newly called function.</span></span>|  
|`STEP_EXCEPTION_FILTER`|<span data-ttu-id="505b3-111">Eine Ausnahme wurde generiert, und die Steuerung wurde an einen Ausnahme Filter übermittelt.</span><span class="sxs-lookup"><span data-stu-id="505b3-111">An exception was generated and control was passed to an exception filter.</span></span>|  
|`STEP_EXCEPTION_HANDLER`|<span data-ttu-id="505b3-112">Eine Ausnahme wurde generiert, und die Steuerung wurde an einen Ausnahmehandler übermittelt.</span><span class="sxs-lookup"><span data-stu-id="505b3-112">An exception was generated and control was passed to an exception handler.</span></span>|  
|`STEP_INTERCEPT`|<span data-ttu-id="505b3-113">Das Steuerelement wurde an einen Interceptor übermittelt.</span><span class="sxs-lookup"><span data-stu-id="505b3-113">Control was passed to an interceptor.</span></span>|  
|`STEP_EXIT`|<span data-ttu-id="505b3-114">Der Thread wurde beendet, bevor der Schritt abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="505b3-114">The thread exited before the step was completed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="505b3-115">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="505b3-115">Requirements</span></span>  
 <span data-ttu-id="505b3-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="505b3-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="505b3-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="505b3-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="505b3-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="505b3-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="505b3-119">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="505b3-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="505b3-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="505b3-120">See also</span></span>

- [<span data-ttu-id="505b3-121">StepComplete-Methode</span><span class="sxs-lookup"><span data-stu-id="505b3-121">StepComplete Method</span></span>](icordebugmanagedcallback-stepcomplete-method.md)
- [<span data-ttu-id="505b3-122">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="505b3-122">Debugging Enumerations</span></span>](debugging-enumerations.md)
