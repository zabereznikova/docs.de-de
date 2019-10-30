---
title: CorDebugExceptionUnwindCallbackType-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugExceptionUnwindCallbackType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionUnwindCallbackType
helpviewer_keywords:
- CorDebugExceptionUnwindCallbackType enumeration [.NET Framework debugging]
ms.assetid: 783dce92-8a98-43db-8f78-888d943dd5b2
topic_type:
- apiref
ms.openlocfilehash: 5004cd293b64436c41caef1c7393d2229d1a6ccf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73098483"
---
# <a name="cordebugexceptionunwindcallbacktype-enumeration"></a><span data-ttu-id="50ed6-102">CorDebugExceptionUnwindCallbackType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="50ed6-102">CorDebugExceptionUnwindCallbackType Enumeration</span></span>
<span data-ttu-id="50ed6-103">Gibt das Ereignis an, das durch den Rückruf während der Entladephase signalisiert wird.</span><span class="sxs-lookup"><span data-stu-id="50ed6-103">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50ed6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="50ed6-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionUnwindCallbackType {  
    DEBUG_EXCEPTION_UNWIND_BEGIN = 1,  
    DEBUG_EXCEPTION_INTERCEPTED  = 2  
} CorDebugExceptionUnwindCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="50ed6-105">Member</span><span class="sxs-lookup"><span data-stu-id="50ed6-105">Members</span></span>  
  
|<span data-ttu-id="50ed6-106">Member</span><span class="sxs-lookup"><span data-stu-id="50ed6-106">Member</span></span>|<span data-ttu-id="50ed6-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="50ed6-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_UNWIND_BEGIN`|<span data-ttu-id="50ed6-108">Der Anfang des Entladevorgangs.</span><span class="sxs-lookup"><span data-stu-id="50ed6-108">The beginning of the unwind process.</span></span>|  
|`DEBUG_EXCEPTION_INTERCEPTED`|<span data-ttu-id="50ed6-109">Die Ausnahme wurde abgefangen.</span><span class="sxs-lookup"><span data-stu-id="50ed6-109">The exception was intercepted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="50ed6-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="50ed6-110">Requirements</span></span>  
 <span data-ttu-id="50ed6-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50ed6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50ed6-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50ed6-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50ed6-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50ed6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50ed6-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50ed6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50ed6-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50ed6-115">See also</span></span>

- [<span data-ttu-id="50ed6-116">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="50ed6-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
