---
title: CorDebugExceptionObjectStackFrame-Struktur
ms.date: 03/30/2017
api_name:
- CorDebugExceptionObjectStackFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionObjectStackFrame
helpviewer_keywords:
- CorDebugExceptionObjectStackFrame structure [.NET Framework debugging]
ms.assetid: 542cdd81-5ae7-4361-b0ef-1ae4775df258
topic_type:
- apiref
ms.openlocfilehash: 7eccaf984b187e463195bb3804f87bbb2c7ad47b
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795923"
---
# <a name="cordebugexceptionobjectstackframe-structure"></a><span data-ttu-id="fbae6-102">CorDebugExceptionObjectStackFrame-Struktur</span><span class="sxs-lookup"><span data-stu-id="fbae6-102">CorDebugExceptionObjectStackFrame Structure</span></span>
<span data-ttu-id="fbae6-103">Stellt Stapelrahmeninformationen von einem Ausnahmeobjekt dar.</span><span class="sxs-lookup"><span data-stu-id="fbae6-103">Represents stack frame information from an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbae6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fbae6-104">Syntax</span></span>  
  
```cpp  
typedef struct CorDebugExceptionObjectStackFrame {  
    ICorDebugModule* pModule;  
    CORDB_ADDRESS ip;  
    mdMethodDef methodDef;  
    BOOL isLastForeignExceptionFrame;  
} CorDebugExceptionObjectStackFrame;  
```  
  
## <a name="members"></a><span data-ttu-id="fbae6-105">Member</span><span class="sxs-lookup"><span data-stu-id="fbae6-105">Members</span></span>  
  
|<span data-ttu-id="fbae6-106">Member</span><span class="sxs-lookup"><span data-stu-id="fbae6-106">Member</span></span>|<span data-ttu-id="fbae6-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fbae6-107">Description</span></span>|  
|------------|-----------------|  
|`pModule`|<span data-ttu-id="fbae6-108">Ein Zeiger auf das ICorDebug Module-Objekt für den aktuellen Frame.</span><span class="sxs-lookup"><span data-stu-id="fbae6-108">A pointer to the ICorDebugModule object for the current frame.</span></span>|  
|`ip`|<span data-ttu-id="fbae6-109">Der Wert des Anweisungs Zeigers (EIP/RIP) für den aktuellen Frame.</span><span class="sxs-lookup"><span data-stu-id="fbae6-109">The value of the instruction pointer (EIP/RIP) for the current frame.</span></span>|  
|`methodDef`|<span data-ttu-id="fbae6-110">Das Methoden Token für den aktuellen Frame.</span><span class="sxs-lookup"><span data-stu-id="fbae6-110">The method token for the current frame.</span></span>|  
|`isLastForeignExceptionFrame`|<span data-ttu-id="fbae6-111">Ein Wert, der angibt, ob der Frame der letzte Frame in einer fremd Ausnahme ist.</span><span class="sxs-lookup"><span data-stu-id="fbae6-111">A value that indicates whether the frame is the last frame in a foreign exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fbae6-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fbae6-112">Remarks</span></span>  
 <span data-ttu-id="fbae6-113">Der Aufrufer muss den Zeiger auf das icorentbugmodule-Objekt freigeben, wenn er nicht mehr verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fbae6-113">The caller must release the pointer to the ICorDebugModule object once it is no longer in use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbae6-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fbae6-114">Requirements</span></span>  
 <span data-ttu-id="fbae6-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbae6-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbae6-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fbae6-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fbae6-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fbae6-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fbae6-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbae6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbae6-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fbae6-119">See also</span></span>

- [<span data-ttu-id="fbae6-120">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="fbae6-120">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="fbae6-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="fbae6-121">Debugging</span></span>](index.md)
