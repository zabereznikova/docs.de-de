---
title: CorDebugIntercept-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugIntercept
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugIntercept
helpviewer_keywords:
- CorDebugIntercept enumeration [.NET Framework debugging]
ms.assetid: 3d5b642e-7ef2-428b-a5ae-509c35ed461a
topic_type:
- apiref
ms.openlocfilehash: 18a5e337b6026a20a95b1c29f3d7bda5187efc66
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795858"
---
# <a name="cordebugintercept-enumeration"></a><span data-ttu-id="00bba-102">CorDebugIntercept-Enumeration</span><span class="sxs-lookup"><span data-stu-id="00bba-102">CorDebugIntercept Enumeration</span></span>
<span data-ttu-id="00bba-103">Gibt die Codetypen an, die schrittweise abgefangen werden können.</span><span class="sxs-lookup"><span data-stu-id="00bba-103">Indicates the types of code that can be intercepted (that is, stepped into).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00bba-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="00bba-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugIntercept {  
    INTERCEPT_NONE                = 0x0,  
    INTERCEPT_CLASS_INIT          = 0x01,  
    INTERCEPT_EXCEPTION_FILTER    = 0x02,  
    INTERCEPT_SECURITY            = 0x04,  
    INTERCEPT_CONTEXT_POLICY      = 0x08,  
    INTERCEPT_INTERCEPTION        = 0x10,  
    INTERCEPT_ALL                 = 0xffff  
} CorDebugIntercept;  
```  
  
## <a name="members"></a><span data-ttu-id="00bba-105">Member</span><span class="sxs-lookup"><span data-stu-id="00bba-105">Members</span></span>  
  
|<span data-ttu-id="00bba-106">Member</span><span class="sxs-lookup"><span data-stu-id="00bba-106">Member</span></span>|<span data-ttu-id="00bba-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="00bba-107">Description</span></span>|  
|------------|-----------------|  
|`INTERCEPT_NONE`|<span data-ttu-id="00bba-108">Kein Code kann abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="00bba-108">No code can be intercepted.</span></span>|  
|`INTERCEPT_CLASS_INIT`|<span data-ttu-id="00bba-109">Ein Konstruktor kann abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="00bba-109">A constructor can be intercepted.</span></span>|  
|`INTERCEPT_EXCEPTION_FILTER`|<span data-ttu-id="00bba-110">Ein Ausnahmefilter kann abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="00bba-110">An exception filter can be intercepted.</span></span>|  
|`INTERCEPT_SECURITY`|<span data-ttu-id="00bba-111">Code, der die Einhaltung von Sicherheitsrichtlinien erzwingt, kann abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="00bba-111">Code that enforces security can be intercepted.</span></span>|  
|`INTERCEPT_CONTEXT_POLICY`|<span data-ttu-id="00bba-112">Eine Kontextrichtlinie kann abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="00bba-112">A context policy can be intercepted.</span></span>|  
|`INTERCEPT_INTERCEPTION`|<span data-ttu-id="00bba-113">Wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="00bba-113">Not used.</span></span>|  
|`INTERCEPT_ALL`|<span data-ttu-id="00bba-114">Jeder Code kann abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="00bba-114">All code can be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00bba-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="00bba-115">Remarks</span></span>  
 <span data-ttu-id="00bba-116">Verwenden Sie die [ICorDebugStepper:: SetInterceptMask](icordebugstepper-setinterceptmask-method.md) -Methode, um die Codetypen festzulegen, die abgefangen werden können.</span><span class="sxs-lookup"><span data-stu-id="00bba-116">Use the [ICorDebugStepper::SetInterceptMask](icordebugstepper-setinterceptmask-method.md) method to establish the types of code that can be intercepted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00bba-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="00bba-117">Requirements</span></span>  
 <span data-ttu-id="00bba-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00bba-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00bba-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00bba-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00bba-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00bba-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00bba-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00bba-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00bba-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="00bba-122">See also</span></span>

- [<span data-ttu-id="00bba-123">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="00bba-123">Debugging Enumerations</span></span>](debugging-enumerations.md)
