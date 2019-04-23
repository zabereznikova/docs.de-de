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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 408e72eeaa1dac83c45488d186425f30c6043280
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59155622"
---
# <a name="cordebugexceptionunwindcallbacktype-enumeration"></a><span data-ttu-id="6aeaa-102">CorDebugExceptionUnwindCallbackType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="6aeaa-102">CorDebugExceptionUnwindCallbackType Enumeration</span></span>
<span data-ttu-id="6aeaa-103">Gibt das Ereignis an, das durch den Rückruf während der Entladephase signalisiert wird.</span><span class="sxs-lookup"><span data-stu-id="6aeaa-103">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6aeaa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6aeaa-104">Syntax</span></span>  
  
```  
typedef enum CorDebugExceptionUnwindCallbackType {  
    DEBUG_EXCEPTION_UNWIND_BEGIN = 1,  
    DEBUG_EXCEPTION_INTERCEPTED  = 2  
} CorDebugExceptionUnwindCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="6aeaa-105">Member</span><span class="sxs-lookup"><span data-stu-id="6aeaa-105">Members</span></span>  
  
|<span data-ttu-id="6aeaa-106">Member</span><span class="sxs-lookup"><span data-stu-id="6aeaa-106">Member</span></span>|<span data-ttu-id="6aeaa-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6aeaa-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_UNWIND_BEGIN`|<span data-ttu-id="6aeaa-108">Der Anfang des Entladeprozesses werden soll.</span><span class="sxs-lookup"><span data-stu-id="6aeaa-108">The beginning of the unwind process.</span></span>|  
|`DEBUG_EXCEPTION_INTERCEPTED`|<span data-ttu-id="6aeaa-109">Die Ausnahme wurde abgefangen.</span><span class="sxs-lookup"><span data-stu-id="6aeaa-109">The exception was intercepted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6aeaa-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6aeaa-110">Requirements</span></span>  
 <span data-ttu-id="6aeaa-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6aeaa-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6aeaa-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6aeaa-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6aeaa-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6aeaa-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6aeaa-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6aeaa-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aeaa-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6aeaa-115">See also</span></span>

- [<span data-ttu-id="6aeaa-116">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="6aeaa-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
