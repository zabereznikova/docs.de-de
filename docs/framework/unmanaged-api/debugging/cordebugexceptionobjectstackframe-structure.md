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
ms.openlocfilehash: 48b15429d40d3a69db52615592fc1697f385d319
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403730"
---
# <a name="cordebugexceptionobjectstackframe-structure"></a><span data-ttu-id="0e806-102">CorDebugExceptionObjectStackFrame-Struktur</span><span class="sxs-lookup"><span data-stu-id="0e806-102">CorDebugExceptionObjectStackFrame Structure</span></span>
<span data-ttu-id="0e806-103">Stellt Stapelrahmeninformationen von einem Ausnahmeobjekt dar.</span><span class="sxs-lookup"><span data-stu-id="0e806-103">Represents stack frame information from an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e806-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0e806-104">Syntax</span></span>  
  
```  
typedef struct CorDebugExceptionObjectStackFrame {  
    ICorDebugModule* pModule;  
    CORDB_ADDRESS ip;  
    mdMethodDef methodDef;  
    BOOL isLastForeignExceptionFrame;  
} CorDebugExceptionObjectStackFrame;  
```  
  
## <a name="members"></a><span data-ttu-id="0e806-105">Member</span><span class="sxs-lookup"><span data-stu-id="0e806-105">Members</span></span>  
  
|<span data-ttu-id="0e806-106">Member</span><span class="sxs-lookup"><span data-stu-id="0e806-106">Member</span></span>|<span data-ttu-id="0e806-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e806-107">Description</span></span>|  
|------------|-----------------|  
|`pModule`|<span data-ttu-id="0e806-108">Ein Zeiger auf das ICorDebugModule-Objekt für den aktuellen Frame.</span><span class="sxs-lookup"><span data-stu-id="0e806-108">A pointer to the ICorDebugModule object for the current frame.</span></span>|  
|`ip`|<span data-ttu-id="0e806-109">Der Wert des Anweisungszeigers (EIP/RIP) für den aktuellen Frame.</span><span class="sxs-lookup"><span data-stu-id="0e806-109">The value of the instruction pointer (EIP/RIP) for the current frame.</span></span>|  
|`methodDef`|<span data-ttu-id="0e806-110">Die Methodentoken für den aktuellen Frame.</span><span class="sxs-lookup"><span data-stu-id="0e806-110">The method token for the current frame.</span></span>|  
|`isLastForeignExceptionFrame`|<span data-ttu-id="0e806-111">Ein Wert, der angibt, ob die Rahmen der letzte Frame in einer fremden Ausnahme ist.</span><span class="sxs-lookup"><span data-stu-id="0e806-111">A value that indicates whether the frame is the last frame in a foreign exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e806-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0e806-112">Remarks</span></span>  
 <span data-ttu-id="0e806-113">Der Aufrufer muss die Zeiger auf das Objekt ICorDebugModule freigeben, sobald es nicht mehr verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0e806-113">The caller must release the pointer to the ICorDebugModule object once it is no longer in use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e806-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0e806-114">Requirements</span></span>  
 <span data-ttu-id="0e806-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e806-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e806-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e806-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e806-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e806-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e806-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e806-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e806-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e806-119">See Also</span></span>  
 [<span data-ttu-id="0e806-120">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="0e806-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="0e806-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="0e806-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
