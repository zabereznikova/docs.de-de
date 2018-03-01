---
title: CorDebugExceptionFlags-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorDebugExceptionFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionFlags
helpviewer_keywords:
- CorDebugExceptionFlags enumeration [.NET Framework debugging]
ms.assetid: b22687a8-e9cf-4e65-a1b0-f92a81bc524e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1b25211c8e7f03cc09e8729abc44af39f0c84259
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugexceptionflags-enumeration"></a><span data-ttu-id="ddf75-102">CorDebugExceptionFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="ddf75-102">CorDebugExceptionFlags Enumeration</span></span>
<span data-ttu-id="ddf75-103">Stellt zusätzliche Informationen über eine Ausnahme bereit.</span><span class="sxs-lookup"><span data-stu-id="ddf75-103">Provides additional information about an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddf75-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ddf75-104">Syntax</span></span>  
  
```  
typedef enum CorDebugExceptionFlags {  
    DEBUG_EXCEPTION_NONE = 0,  
    DEBUG_EXCEPTION_CAN_BE_INTERCEPTED = 0x0001  
} CorDebugExceptionFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="ddf75-105">Member</span><span class="sxs-lookup"><span data-stu-id="ddf75-105">Members</span></span>  
  
|<span data-ttu-id="ddf75-106">Member</span><span class="sxs-lookup"><span data-stu-id="ddf75-106">Member</span></span>|<span data-ttu-id="ddf75-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ddf75-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_NONE`|<span data-ttu-id="ddf75-108">Es ist keine Ausnahme vorhanden.</span><span class="sxs-lookup"><span data-stu-id="ddf75-108">There is no exception.</span></span>|  
|`DEBUG_EXCEPTION_CAN_BE_INTERCEPTED`|<span data-ttu-id="ddf75-109">Die Ausnahme kann abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="ddf75-109">The exception is interceptable.</span></span><br /><br /> <span data-ttu-id="ddf75-110">Die Zeitsteuerung der Ausnahme bewirkt möglicherweise immer noch, dass der Debugger sie nicht abfangen kann.</span><span class="sxs-lookup"><span data-stu-id="ddf75-110">The timing of the exception may still be such that the debugger cannot intercept it.</span></span> <span data-ttu-id="ddf75-111">Wenn z. B. unter dem aktuellen Rückruf kein verwalteter Code vorliegt oder wenn das Ausnahmeereignis aus einer JIT-Anlage (Just-in-Time) resultierte, kann die Ausnahme nicht abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="ddf75-111">For example, if there is no managed code below the current callback or the exception event resulted from a just-in-time (JIT) attachment, the exception cannot be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ddf75-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ddf75-112">Remarks</span></span>  
 <span data-ttu-id="ddf75-113">In späteren Versionen werden dieser Enumeration möglicherweise neue Werte hinzugefügt, daher sollten Sie in Ihrem Code `CorDebugExceptionFlags` für unerwartete Werte verwenden.</span><span class="sxs-lookup"><span data-stu-id="ddf75-113">New values may be added to this enumeration in later versions, so you should prepare code that uses `CorDebugExceptionFlags` for unexpected values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddf75-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ddf75-114">Requirements</span></span>  
 <span data-ttu-id="ddf75-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ddf75-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddf75-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ddf75-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ddf75-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ddf75-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ddf75-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddf75-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddf75-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ddf75-119">See Also</span></span>  
 [<span data-ttu-id="ddf75-120">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="ddf75-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
