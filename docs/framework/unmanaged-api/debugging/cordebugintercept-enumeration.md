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
ms.openlocfilehash: 3d3d4af8e9ee073c0aefec418a3b53c4589adf0d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729108"
---
# <a name="cordebugintercept-enumeration"></a><span data-ttu-id="9133b-102">CorDebugIntercept-Enumeration</span><span class="sxs-lookup"><span data-stu-id="9133b-102">CorDebugIntercept Enumeration</span></span>

<span data-ttu-id="9133b-103">Gibt die Codetypen an, die schrittweise abgefangen werden können.</span><span class="sxs-lookup"><span data-stu-id="9133b-103">Indicates the types of code that can be intercepted (that is, stepped into).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9133b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9133b-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="9133b-105">Member</span><span class="sxs-lookup"><span data-stu-id="9133b-105">Members</span></span>  
  
|<span data-ttu-id="9133b-106">Member</span><span class="sxs-lookup"><span data-stu-id="9133b-106">Member</span></span>|<span data-ttu-id="9133b-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9133b-107">Description</span></span>|  
|------------|-----------------|  
|`INTERCEPT_NONE`|<span data-ttu-id="9133b-108">Kein Code kann abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="9133b-108">No code can be intercepted.</span></span>|  
|`INTERCEPT_CLASS_INIT`|<span data-ttu-id="9133b-109">Ein Konstruktor kann abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="9133b-109">A constructor can be intercepted.</span></span>|  
|`INTERCEPT_EXCEPTION_FILTER`|<span data-ttu-id="9133b-110">Ein Ausnahmefilter kann abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="9133b-110">An exception filter can be intercepted.</span></span>|  
|`INTERCEPT_SECURITY`|<span data-ttu-id="9133b-111">Code, der die Einhaltung von Sicherheitsrichtlinien erzwingt, kann abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="9133b-111">Code that enforces security can be intercepted.</span></span>|  
|`INTERCEPT_CONTEXT_POLICY`|<span data-ttu-id="9133b-112">Eine Kontextrichtlinie kann abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="9133b-112">A context policy can be intercepted.</span></span>|  
|`INTERCEPT_INTERCEPTION`|<span data-ttu-id="9133b-113">Wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="9133b-113">Not used.</span></span>|  
|`INTERCEPT_ALL`|<span data-ttu-id="9133b-114">Jeder Code kann abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="9133b-114">All code can be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9133b-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9133b-115">Remarks</span></span>  

 <span data-ttu-id="9133b-116">Verwenden Sie die [ICorDebugStepper:: SetInterceptMask](icordebugstepper-setinterceptmask-method.md) -Methode, um die Codetypen festzulegen, die abgefangen werden können.</span><span class="sxs-lookup"><span data-stu-id="9133b-116">Use the [ICorDebugStepper::SetInterceptMask](icordebugstepper-setinterceptmask-method.md) method to establish the types of code that can be intercepted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9133b-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9133b-117">Requirements</span></span>  

 <span data-ttu-id="9133b-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9133b-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9133b-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9133b-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9133b-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9133b-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9133b-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9133b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9133b-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9133b-122">See also</span></span>

- [<span data-ttu-id="9133b-123">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="9133b-123">Debugging Enumerations</span></span>](debugging-enumerations.md)
