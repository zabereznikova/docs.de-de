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
ms.openlocfilehash: 32892a14de820e8add38654cef92aa44930aec62
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugstepreason-enumeration"></a><span data-ttu-id="0d6f7-102">CorDebugStepReason-Enumeration</span><span class="sxs-lookup"><span data-stu-id="0d6f7-102">CorDebugStepReason Enumeration</span></span>
<span data-ttu-id="0d6f7-103">Gibt das Ergebnis eines einzelnen Schritts an.</span><span class="sxs-lookup"><span data-stu-id="0d6f7-103">Indicates the outcome of an individual step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d6f7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0d6f7-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="0d6f7-105">Member</span><span class="sxs-lookup"><span data-stu-id="0d6f7-105">Members</span></span>  
  
|<span data-ttu-id="0d6f7-106">Member</span><span class="sxs-lookup"><span data-stu-id="0d6f7-106">Member</span></span>|<span data-ttu-id="0d6f7-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0d6f7-107">Description</span></span>|  
|------------|-----------------|  
|`STEP_NORMAL`|<span data-ttu-id="0d6f7-108">Ausführen in Einzelschritten werden normalerweise innerhalb der gleichen Funktion abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="0d6f7-108">Stepping completed normally, within the same function.</span></span>|  
|`STEP_RETURN`|<span data-ttu-id="0d6f7-109">Ausführen in Einzelschritten Fortsetzung normalerweise, nachdem die Funktion zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0d6f7-109">Stepping continued normally, after the function returned.</span></span>|  
|`STEP_CALL`|<span data-ttu-id="0d6f7-110">Ausführen in Einzelschritten wurde am Anfang einer neu aufgerufenen Funktion normal fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="0d6f7-110">Stepping continued normally, at the beginning of a newly called function.</span></span>|  
|`STEP_EXCEPTION_FILTER`|<span data-ttu-id="0d6f7-111">Eine Ausnahme wurde generiert und die Kontrolle an einen Ausnahmefilter übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="0d6f7-111">An exception was generated and control was passed to an exception filter.</span></span>|  
|`STEP_EXCEPTION_HANDLER`|<span data-ttu-id="0d6f7-112">Eine Ausnahme wurde generiert und die Kontrolle zu einem Ausnahmehandler übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="0d6f7-112">An exception was generated and control was passed to an exception handler.</span></span>|  
|`STEP_INTERCEPT`|<span data-ttu-id="0d6f7-113">Steuerelement wurde an einen Interceptor übergeben.</span><span class="sxs-lookup"><span data-stu-id="0d6f7-113">Control was passed to an interceptor.</span></span>|  
|`STEP_EXIT`|<span data-ttu-id="0d6f7-114">Der Thread wurde beendet, bevor der Schritt abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="0d6f7-114">The thread exited before the step was completed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0d6f7-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0d6f7-115">Requirements</span></span>  
 <span data-ttu-id="0d6f7-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d6f7-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d6f7-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0d6f7-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0d6f7-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d6f7-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d6f7-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d6f7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d6f7-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0d6f7-120">See Also</span></span>  
 [<span data-ttu-id="0d6f7-121">StepComplete-Methode</span><span class="sxs-lookup"><span data-stu-id="0d6f7-121">StepComplete Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)  
 [<span data-ttu-id="0d6f7-122">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="0d6f7-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
