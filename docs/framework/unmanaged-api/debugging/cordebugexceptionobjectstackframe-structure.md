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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5cd2add7e96a8edaff8509563ae1846e80132001
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740098"
---
# <a name="cordebugexceptionobjectstackframe-structure"></a><span data-ttu-id="9dcd1-102">CorDebugExceptionObjectStackFrame-Struktur</span><span class="sxs-lookup"><span data-stu-id="9dcd1-102">CorDebugExceptionObjectStackFrame Structure</span></span>
<span data-ttu-id="9dcd1-103">Stellt Stapelrahmeninformationen von einem Ausnahmeobjekt dar.</span><span class="sxs-lookup"><span data-stu-id="9dcd1-103">Represents stack frame information from an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dcd1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9dcd1-104">Syntax</span></span>  
  
```cpp  
typedef struct CorDebugExceptionObjectStackFrame {  
    ICorDebugModule* pModule;  
    CORDB_ADDRESS ip;  
    mdMethodDef methodDef;  
    BOOL isLastForeignExceptionFrame;  
} CorDebugExceptionObjectStackFrame;  
```  
  
## <a name="members"></a><span data-ttu-id="9dcd1-105">Member</span><span class="sxs-lookup"><span data-stu-id="9dcd1-105">Members</span></span>  
  
|<span data-ttu-id="9dcd1-106">Member</span><span class="sxs-lookup"><span data-stu-id="9dcd1-106">Member</span></span>|<span data-ttu-id="9dcd1-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9dcd1-107">Description</span></span>|  
|------------|-----------------|  
|`pModule`|<span data-ttu-id="9dcd1-108">Ein Zeiger auf das ICorDebugModule-Objekt, für den aktuellen Frame.</span><span class="sxs-lookup"><span data-stu-id="9dcd1-108">A pointer to the ICorDebugModule object for the current frame.</span></span>|  
|`ip`|<span data-ttu-id="9dcd1-109">Der Wert des Anweisungszeigers (EIP/RIP) für den aktuellen Frame.</span><span class="sxs-lookup"><span data-stu-id="9dcd1-109">The value of the instruction pointer (EIP/RIP) for the current frame.</span></span>|  
|`methodDef`|<span data-ttu-id="9dcd1-110">Die Methodentoken für den aktuellen Frame.</span><span class="sxs-lookup"><span data-stu-id="9dcd1-110">The method token for the current frame.</span></span>|  
|`isLastForeignExceptionFrame`|<span data-ttu-id="9dcd1-111">Ein Wert, der angibt, ob der Rahmen der letzte Frame in einer foreign-Ausnahme ist.</span><span class="sxs-lookup"><span data-stu-id="9dcd1-111">A value that indicates whether the frame is the last frame in a foreign exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9dcd1-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9dcd1-112">Remarks</span></span>  
 <span data-ttu-id="9dcd1-113">Der Aufrufer muss den Zeiger auf das Objekt ICorDebugModule freigeben, sobald es nicht mehr verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9dcd1-113">The caller must release the pointer to the ICorDebugModule object once it is no longer in use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9dcd1-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9dcd1-114">Requirements</span></span>  
 <span data-ttu-id="9dcd1-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9dcd1-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9dcd1-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9dcd1-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9dcd1-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9dcd1-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9dcd1-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9dcd1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dcd1-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9dcd1-119">See also</span></span>

- [<span data-ttu-id="9dcd1-120">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="9dcd1-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="9dcd1-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="9dcd1-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
