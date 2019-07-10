---
title: CorDebugExceptionCallbackType-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugExceptionCallbackType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionCallbackType
helpviewer_keywords:
- CorDebugExceptionCallbackType enumeration [.NET Framework debugging]
ms.assetid: 4d946ad4-3c19-42cb-bec9-8633325ba769
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b712ee0bb8e67f448b7ea2bee3c092367181abad
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740212"
---
# <a name="cordebugexceptioncallbacktype-enumeration"></a><span data-ttu-id="de380-102">CorDebugExceptionCallbackType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="de380-102">CorDebugExceptionCallbackType Enumeration</span></span>
<span data-ttu-id="de380-103">Gibt den Typ der Rückruf, der von erfolgt eine [ICorDebugManagedCallback2:: Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) Ereignis.</span><span class="sxs-lookup"><span data-stu-id="de380-103">Indicates the type of callback that is made from an [ICorDebugManagedCallback2::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de380-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="de380-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionCallbackType {  
    DEBUG_EXCEPTION_FIRST_CHANCE         = 1,  
    DEBUG_EXCEPTION_USER_FIRST_CHANCE    = 2,  
    DEBUG_EXCEPTION_CATCH_HANDLER_FOUND  = 3,  
    DEBUG_EXCEPTION_UNHANDLED            = 4  
} CorDebugExceptionCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="de380-105">Member</span><span class="sxs-lookup"><span data-stu-id="de380-105">Members</span></span>  
  
|<span data-ttu-id="de380-106">Member</span><span class="sxs-lookup"><span data-stu-id="de380-106">Member</span></span>|<span data-ttu-id="de380-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="de380-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="de380-108">Es wurde eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="de380-108">An exception was thrown.</span></span>|  
|`DEBUG_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="de380-109">Die Ausnahmeabschlussprozess Benutzercode.</span><span class="sxs-lookup"><span data-stu-id="de380-109">The exception windup process entered user code.</span></span>|  
|`DEBUG_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="de380-110">Der Ausnahmeabschlussprozess finden Sie eine `catch` im Benutzercode blockiert.</span><span class="sxs-lookup"><span data-stu-id="de380-110">The exception windup process found a `catch` block in user code.</span></span>|  
|`DEBUG_EXCEPTION_UNHANDLED`|<span data-ttu-id="de380-111">Die Ausnahme wurde nicht behandelt.</span><span class="sxs-lookup"><span data-stu-id="de380-111">The exception was not handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="de380-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="de380-112">Requirements</span></span>  
 <span data-ttu-id="de380-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de380-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de380-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de380-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de380-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de380-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de380-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de380-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de380-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de380-117">See also</span></span>

- [<span data-ttu-id="de380-118">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="de380-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
