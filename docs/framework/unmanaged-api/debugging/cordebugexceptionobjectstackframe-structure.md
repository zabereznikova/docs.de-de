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
ms.openlocfilehash: 2845c15d67e287d6efb0cd0a9c940b69de3a1c0c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789378"
---
# <a name="cordebugexceptionobjectstackframe-structure"></a><span data-ttu-id="c3a3e-102">CorDebugExceptionObjectStackFrame-Struktur</span><span class="sxs-lookup"><span data-stu-id="c3a3e-102">CorDebugExceptionObjectStackFrame Structure</span></span>
<span data-ttu-id="c3a3e-103">Stellt Stapelrahmeninformationen von einem Ausnahmeobjekt dar.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-103">Represents stack frame information from an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3a3e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c3a3e-104">Syntax</span></span>  
  
```cpp  
typedef struct CorDebugExceptionObjectStackFrame {  
    ICorDebugModule* pModule;  
    CORDB_ADDRESS ip;  
    mdMethodDef methodDef;  
    BOOL isLastForeignExceptionFrame;  
} CorDebugExceptionObjectStackFrame;  
```  
  
## <a name="members"></a><span data-ttu-id="c3a3e-105">Member</span><span class="sxs-lookup"><span data-stu-id="c3a3e-105">Members</span></span>  
  
|<span data-ttu-id="c3a3e-106">Member</span><span class="sxs-lookup"><span data-stu-id="c3a3e-106">Member</span></span>|<span data-ttu-id="c3a3e-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c3a3e-107">Description</span></span>|  
|------------|-----------------|  
|`pModule`|<span data-ttu-id="c3a3e-108">Ein Zeiger auf das ICorDebug Module-Objekt für den aktuellen Frame.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-108">A pointer to the ICorDebugModule object for the current frame.</span></span>|  
|`ip`|<span data-ttu-id="c3a3e-109">Der Wert des Anweisungs Zeigers (EIP/RIP) für den aktuellen Frame.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-109">The value of the instruction pointer (EIP/RIP) for the current frame.</span></span>|  
|`methodDef`|<span data-ttu-id="c3a3e-110">Das Methoden Token für den aktuellen Frame.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-110">The method token for the current frame.</span></span>|  
|`isLastForeignExceptionFrame`|<span data-ttu-id="c3a3e-111">Ein Wert, der angibt, ob der Frame der letzte Frame in einer fremd Ausnahme ist.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-111">A value that indicates whether the frame is the last frame in a foreign exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3a3e-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c3a3e-112">Remarks</span></span>  
 <span data-ttu-id="c3a3e-113">Der Aufrufer muss den Zeiger auf das icorentbugmodule-Objekt freigeben, wenn er nicht mehr verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c3a3e-113">The caller must release the pointer to the ICorDebugModule object once it is no longer in use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3a3e-114">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c3a3e-114">Requirements</span></span>  
 <span data-ttu-id="c3a3e-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3a3e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3a3e-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c3a3e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c3a3e-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3a3e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3a3e-118">**.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3a3e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3a3e-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3a3e-119">See also</span></span>

- [<span data-ttu-id="c3a3e-120">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="c3a3e-120">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="c3a3e-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="c3a3e-121">Debugging</span></span>](index.md)
