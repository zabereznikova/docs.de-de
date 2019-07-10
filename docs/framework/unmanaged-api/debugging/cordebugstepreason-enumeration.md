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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d9dc94689083d79858319387747eb9dafe8b2f6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739561"
---
# <a name="cordebugstepreason-enumeration"></a><span data-ttu-id="75621-102">CorDebugStepReason-Enumeration</span><span class="sxs-lookup"><span data-stu-id="75621-102">CorDebugStepReason Enumeration</span></span>
<span data-ttu-id="75621-103">Gibt das Ergebnis eines einzelnen Schritts an.</span><span class="sxs-lookup"><span data-stu-id="75621-103">Indicates the outcome of an individual step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75621-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="75621-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="75621-105">Member</span><span class="sxs-lookup"><span data-stu-id="75621-105">Members</span></span>  
  
|<span data-ttu-id="75621-106">Member</span><span class="sxs-lookup"><span data-stu-id="75621-106">Member</span></span>|<span data-ttu-id="75621-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="75621-107">Description</span></span>|  
|------------|-----------------|  
|`STEP_NORMAL`|<span data-ttu-id="75621-108">Schrittweises durchlaufen werden normalerweise innerhalb der gleichen Funktion abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="75621-108">Stepping completed normally, within the same function.</span></span>|  
|`STEP_RETURN`|<span data-ttu-id="75621-109">Schrittweise ausführen werden normalerweise nach der Rückgabe der Funktion fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="75621-109">Stepping continued normally, after the function returned.</span></span>|  
|`STEP_CALL`|<span data-ttu-id="75621-110">Stepping weiterhin in der Regel am Anfang einer neu aufgerufenen Funktion.</span><span class="sxs-lookup"><span data-stu-id="75621-110">Stepping continued normally, at the beginning of a newly called function.</span></span>|  
|`STEP_EXCEPTION_FILTER`|<span data-ttu-id="75621-111">Eine Ausnahme wurde generiert, und Kontrolle an einen Ausnahmefilter übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="75621-111">An exception was generated and control was passed to an exception filter.</span></span>|  
|`STEP_EXCEPTION_HANDLER`|<span data-ttu-id="75621-112">Eine Ausnahme wurde generiert, und Steuerelement zu einem Ausnahmehandler übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="75621-112">An exception was generated and control was passed to an exception handler.</span></span>|  
|`STEP_INTERCEPT`|<span data-ttu-id="75621-113">Steuerelement wurde an einen Interceptor übergeben.</span><span class="sxs-lookup"><span data-stu-id="75621-113">Control was passed to an interceptor.</span></span>|  
|`STEP_EXIT`|<span data-ttu-id="75621-114">Der Thread beendet wurde, bevor der Schritt abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="75621-114">The thread exited before the step was completed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="75621-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="75621-115">Requirements</span></span>  
 <span data-ttu-id="75621-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75621-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75621-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="75621-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75621-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75621-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75621-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75621-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75621-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75621-120">See also</span></span>

- [<span data-ttu-id="75621-121">StepComplete-Methode</span><span class="sxs-lookup"><span data-stu-id="75621-121">StepComplete Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)
- [<span data-ttu-id="75621-122">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="75621-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
