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
ms.openlocfilehash: 50903b3737c0fc63eda2b1190e4c3d961ce3ae7b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726040"
---
# <a name="cordebugstepreason-enumeration"></a><span data-ttu-id="71a5d-102">CorDebugStepReason-Enumeration</span><span class="sxs-lookup"><span data-stu-id="71a5d-102">CorDebugStepReason Enumeration</span></span>

<span data-ttu-id="71a5d-103">Gibt das Ergebnis eines einzelnen Schritts an.</span><span class="sxs-lookup"><span data-stu-id="71a5d-103">Indicates the outcome of an individual step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71a5d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="71a5d-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="71a5d-105">Member</span><span class="sxs-lookup"><span data-stu-id="71a5d-105">Members</span></span>  
  
|<span data-ttu-id="71a5d-106">Member</span><span class="sxs-lookup"><span data-stu-id="71a5d-106">Member</span></span>|<span data-ttu-id="71a5d-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="71a5d-107">Description</span></span>|  
|------------|-----------------|  
|`STEP_NORMAL`|<span data-ttu-id="71a5d-108">Die schrittweise Ausführung erfolgt in derselben Funktion.</span><span class="sxs-lookup"><span data-stu-id="71a5d-108">Stepping completed normally, within the same function.</span></span>|  
|`STEP_RETURN`|<span data-ttu-id="71a5d-109">Die schrittweise Ausführung wird nach der Rückgabe der Funktion fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="71a5d-109">Stepping continued normally, after the function returned.</span></span>|  
|`STEP_CALL`|<span data-ttu-id="71a5d-110">Schrittweise Fortsetzung am Anfang einer neu aufgerufenen Funktion.</span><span class="sxs-lookup"><span data-stu-id="71a5d-110">Stepping continued normally, at the beginning of a newly called function.</span></span>|  
|`STEP_EXCEPTION_FILTER`|<span data-ttu-id="71a5d-111">Eine Ausnahme wurde generiert, und die Steuerung wurde an einen Ausnahme Filter übermittelt.</span><span class="sxs-lookup"><span data-stu-id="71a5d-111">An exception was generated and control was passed to an exception filter.</span></span>|  
|`STEP_EXCEPTION_HANDLER`|<span data-ttu-id="71a5d-112">Eine Ausnahme wurde generiert, und die Steuerung wurde an einen Ausnahmehandler übermittelt.</span><span class="sxs-lookup"><span data-stu-id="71a5d-112">An exception was generated and control was passed to an exception handler.</span></span>|  
|`STEP_INTERCEPT`|<span data-ttu-id="71a5d-113">Das Steuerelement wurde an einen Interceptor übermittelt.</span><span class="sxs-lookup"><span data-stu-id="71a5d-113">Control was passed to an interceptor.</span></span>|  
|`STEP_EXIT`|<span data-ttu-id="71a5d-114">Der Thread wurde beendet, bevor der Schritt abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="71a5d-114">The thread exited before the step was completed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="71a5d-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="71a5d-115">Requirements</span></span>  

 <span data-ttu-id="71a5d-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71a5d-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71a5d-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71a5d-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71a5d-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71a5d-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71a5d-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71a5d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71a5d-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="71a5d-120">See also</span></span>

- [<span data-ttu-id="71a5d-121">StepComplete-Methode</span><span class="sxs-lookup"><span data-stu-id="71a5d-121">StepComplete Method</span></span>](icordebugmanagedcallback-stepcomplete-method.md)
- [<span data-ttu-id="71a5d-122">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="71a5d-122">Debugging Enumerations</span></span>](debugging-enumerations.md)
