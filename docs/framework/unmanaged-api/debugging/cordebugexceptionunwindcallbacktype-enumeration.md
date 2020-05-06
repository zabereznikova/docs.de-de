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
ms.openlocfilehash: 4d2be9960f8935b754791a8badd4ea98b5d54912
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795910"
---
# <a name="cordebugexceptionunwindcallbacktype-enumeration"></a><span data-ttu-id="1405a-102">CorDebugExceptionUnwindCallbackType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1405a-102">CorDebugExceptionUnwindCallbackType Enumeration</span></span>
<span data-ttu-id="1405a-103">Gibt das Ereignis an, das durch den Rückruf während der Entladephase signalisiert wird.</span><span class="sxs-lookup"><span data-stu-id="1405a-103">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1405a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1405a-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionUnwindCallbackType {  
    DEBUG_EXCEPTION_UNWIND_BEGIN = 1,  
    DEBUG_EXCEPTION_INTERCEPTED  = 2  
} CorDebugExceptionUnwindCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="1405a-105">Member</span><span class="sxs-lookup"><span data-stu-id="1405a-105">Members</span></span>  
  
|<span data-ttu-id="1405a-106">Member</span><span class="sxs-lookup"><span data-stu-id="1405a-106">Member</span></span>|<span data-ttu-id="1405a-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1405a-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_UNWIND_BEGIN`|<span data-ttu-id="1405a-108">Der Anfang des Entladevorgangs.</span><span class="sxs-lookup"><span data-stu-id="1405a-108">The beginning of the unwind process.</span></span>|  
|`DEBUG_EXCEPTION_INTERCEPTED`|<span data-ttu-id="1405a-109">Die Ausnahme wurde abgefangen.</span><span class="sxs-lookup"><span data-stu-id="1405a-109">The exception was intercepted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1405a-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1405a-110">Requirements</span></span>  
 <span data-ttu-id="1405a-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1405a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1405a-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1405a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1405a-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1405a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1405a-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1405a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1405a-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1405a-115">See also</span></span>

- [<span data-ttu-id="1405a-116">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="1405a-116">Debugging Enumerations</span></span>](debugging-enumerations.md)
