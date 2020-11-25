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
ms.openlocfilehash: cddcf66939a2ae7ab9e7f63a6fd61b72c56f6c7a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712728"
---
# <a name="cordebugexceptioncallbacktype-enumeration"></a><span data-ttu-id="fce1d-102">CorDebugExceptionCallbackType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="fce1d-102">CorDebugExceptionCallbackType Enumeration</span></span>

<span data-ttu-id="fce1d-103">Gibt den Typ des Rückrufs an, der von einem [ICorDebugManagedCallback2:: Exception](icordebugmanagedcallback2-exception-method.md) -Ereignis stammt.</span><span class="sxs-lookup"><span data-stu-id="fce1d-103">Indicates the type of callback that is made from an [ICorDebugManagedCallback2::Exception](icordebugmanagedcallback2-exception-method.md) event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fce1d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fce1d-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionCallbackType {  
    DEBUG_EXCEPTION_FIRST_CHANCE         = 1,  
    DEBUG_EXCEPTION_USER_FIRST_CHANCE    = 2,  
    DEBUG_EXCEPTION_CATCH_HANDLER_FOUND  = 3,  
    DEBUG_EXCEPTION_UNHANDLED            = 4  
} CorDebugExceptionCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="fce1d-105">Member</span><span class="sxs-lookup"><span data-stu-id="fce1d-105">Members</span></span>  
  
|<span data-ttu-id="fce1d-106">Member</span><span class="sxs-lookup"><span data-stu-id="fce1d-106">Member</span></span>|<span data-ttu-id="fce1d-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fce1d-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="fce1d-108">Eine Ausnahme wurde ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="fce1d-108">An exception was thrown.</span></span>|  
|`DEBUG_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="fce1d-109">Der windup-Ausnahme Prozess hat den Benutzercode eingegeben.</span><span class="sxs-lookup"><span data-stu-id="fce1d-109">The exception windup process entered user code.</span></span>|  
|`DEBUG_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="fce1d-110">Der windup-Ausnahme Prozess hat einen `catch` Block im Benutzercode gefunden.</span><span class="sxs-lookup"><span data-stu-id="fce1d-110">The exception windup process found a `catch` block in user code.</span></span>|  
|`DEBUG_EXCEPTION_UNHANDLED`|<span data-ttu-id="fce1d-111">Die Ausnahme wurde nicht behandelt.</span><span class="sxs-lookup"><span data-stu-id="fce1d-111">The exception was not handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fce1d-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fce1d-112">Requirements</span></span>  

 <span data-ttu-id="fce1d-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fce1d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fce1d-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fce1d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fce1d-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fce1d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fce1d-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fce1d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fce1d-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fce1d-117">See also</span></span>

- [<span data-ttu-id="fce1d-118">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="fce1d-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
