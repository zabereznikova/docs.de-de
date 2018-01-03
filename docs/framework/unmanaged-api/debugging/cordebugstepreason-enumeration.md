---
title: CorDebugStepReason-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugStepReason
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugStepReason
helpviewer_keywords: CorDebugStepReason enumeration [.NET Framework debugging]
ms.assetid: fe248069-b33c-48e1-a777-06ac9b239c54
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 68c4f9452f8ccc9b4d48ee67755a311f32540247
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugstepreason-enumeration"></a><span data-ttu-id="8645c-102">CorDebugStepReason-Enumeration</span><span class="sxs-lookup"><span data-stu-id="8645c-102">CorDebugStepReason Enumeration</span></span>
<span data-ttu-id="8645c-103">Gibt das Ergebnis eines einzelnen Schritts an.</span><span class="sxs-lookup"><span data-stu-id="8645c-103">Indicates the outcome of an individual step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8645c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8645c-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="8645c-105">Member</span><span class="sxs-lookup"><span data-stu-id="8645c-105">Members</span></span>  
  
|<span data-ttu-id="8645c-106">Member</span><span class="sxs-lookup"><span data-stu-id="8645c-106">Member</span></span>|<span data-ttu-id="8645c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8645c-107">Description</span></span>|  
|------------|-----------------|  
|`STEP_NORMAL`|<span data-ttu-id="8645c-108">Ausführen in Einzelschritten werden normalerweise innerhalb der gleichen Funktion abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="8645c-108">Stepping completed normally, within the same function.</span></span>|  
|`STEP_RETURN`|<span data-ttu-id="8645c-109">Ausführen in Einzelschritten Fortsetzung normalerweise, nachdem die Funktion zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8645c-109">Stepping continued normally, after the function returned.</span></span>|  
|`STEP_CALL`|<span data-ttu-id="8645c-110">Ausführen in Einzelschritten wurde am Anfang einer neu aufgerufenen Funktion normal fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="8645c-110">Stepping continued normally, at the beginning of a newly called function.</span></span>|  
|`STEP_EXCEPTION_FILTER`|<span data-ttu-id="8645c-111">Eine Ausnahme wurde generiert und die Kontrolle an einen Ausnahmefilter übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="8645c-111">An exception was generated and control was passed to an exception filter.</span></span>|  
|`STEP_EXCEPTION_HANDLER`|<span data-ttu-id="8645c-112">Eine Ausnahme wurde generiert und die Kontrolle zu einem Ausnahmehandler übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="8645c-112">An exception was generated and control was passed to an exception handler.</span></span>|  
|`STEP_INTERCEPT`|<span data-ttu-id="8645c-113">Steuerelement wurde an einen Interceptor übergeben.</span><span class="sxs-lookup"><span data-stu-id="8645c-113">Control was passed to an interceptor.</span></span>|  
|`STEP_EXIT`|<span data-ttu-id="8645c-114">Der Thread wurde beendet, bevor der Schritt abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="8645c-114">The thread exited before the step was completed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8645c-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8645c-115">Requirements</span></span>  
 <span data-ttu-id="8645c-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8645c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8645c-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8645c-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8645c-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8645c-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8645c-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8645c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8645c-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8645c-120">See Also</span></span>  
 [<span data-ttu-id="8645c-121">StepComplete-Methode</span><span class="sxs-lookup"><span data-stu-id="8645c-121">StepComplete Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)  
 [<span data-ttu-id="8645c-122">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="8645c-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
