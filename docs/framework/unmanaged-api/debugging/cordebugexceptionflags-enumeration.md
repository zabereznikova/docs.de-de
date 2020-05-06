---
title: CorDebugExceptionFlags-Enumeration
ms.date: 03/30/2017
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
ms.openlocfilehash: 45de821dd52f7e153fc79ffde056ed959c654fce
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795947"
---
# <a name="cordebugexceptionflags-enumeration"></a><span data-ttu-id="daf44-102">CorDebugExceptionFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="daf44-102">CorDebugExceptionFlags Enumeration</span></span>
<span data-ttu-id="daf44-103">Stellt zusätzliche Informationen über eine Ausnahme bereit.</span><span class="sxs-lookup"><span data-stu-id="daf44-103">Provides additional information about an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="daf44-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="daf44-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionFlags {  
    DEBUG_EXCEPTION_NONE = 0,  
    DEBUG_EXCEPTION_CAN_BE_INTERCEPTED = 0x0001  
} CorDebugExceptionFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="daf44-105">Member</span><span class="sxs-lookup"><span data-stu-id="daf44-105">Members</span></span>  
  
|<span data-ttu-id="daf44-106">Member</span><span class="sxs-lookup"><span data-stu-id="daf44-106">Member</span></span>|<span data-ttu-id="daf44-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="daf44-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_NONE`|<span data-ttu-id="daf44-108">Es ist keine Ausnahme vorhanden.</span><span class="sxs-lookup"><span data-stu-id="daf44-108">There is no exception.</span></span>|  
|`DEBUG_EXCEPTION_CAN_BE_INTERCEPTED`|<span data-ttu-id="daf44-109">Die Ausnahme kann abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="daf44-109">The exception is interceptable.</span></span><br /><br /> <span data-ttu-id="daf44-110">Die Zeitsteuerung der Ausnahme bewirkt möglicherweise immer noch, dass der Debugger sie nicht abfangen kann.</span><span class="sxs-lookup"><span data-stu-id="daf44-110">The timing of the exception may still be such that the debugger cannot intercept it.</span></span> <span data-ttu-id="daf44-111">Wenn z. B. unter dem aktuellen Rückruf kein verwalteter Code vorliegt oder wenn das Ausnahmeereignis aus einer JIT-Anlage (Just-in-Time) resultierte, kann die Ausnahme nicht abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="daf44-111">For example, if there is no managed code below the current callback or the exception event resulted from a just-in-time (JIT) attachment, the exception cannot be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="daf44-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="daf44-112">Remarks</span></span>  
 <span data-ttu-id="daf44-113">In späteren Versionen werden dieser Enumeration möglicherweise neue Werte hinzugefügt, daher sollten Sie in Ihrem Code `CorDebugExceptionFlags` für unerwartete Werte verwenden.</span><span class="sxs-lookup"><span data-stu-id="daf44-113">New values may be added to this enumeration in later versions, so you should prepare code that uses `CorDebugExceptionFlags` for unexpected values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="daf44-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="daf44-114">Requirements</span></span>  
 <span data-ttu-id="daf44-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="daf44-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="daf44-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="daf44-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="daf44-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="daf44-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="daf44-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="daf44-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daf44-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="daf44-119">See also</span></span>

- [<span data-ttu-id="daf44-120">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="daf44-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
