---
title: CorDebugExceptionObjectStackFrame-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugExceptionObjectStackFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugExceptionObjectStackFrame
helpviewer_keywords: CorDebugExceptionObjectStackFrame structure [.NET Framework debugging]
ms.assetid: 542cdd81-5ae7-4361-b0ef-1ae4775df258
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cf166f606aa2c0e0900356395c36bd6875897e3d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugexceptionobjectstackframe-structure"></a><span data-ttu-id="4b18e-102">CorDebugExceptionObjectStackFrame-Struktur</span><span class="sxs-lookup"><span data-stu-id="4b18e-102">CorDebugExceptionObjectStackFrame Structure</span></span>
<span data-ttu-id="4b18e-103">Stellt Stapelrahmeninformationen von einem Ausnahmeobjekt dar.</span><span class="sxs-lookup"><span data-stu-id="4b18e-103">Represents stack frame information from an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b18e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b18e-104">Syntax</span></span>  
  
```  
typedef struct CorDebugExceptionObjectStackFrame {  
    ICorDebugModule* pModule;  
    CORDB_ADDRESS ip;  
    mdMethodDef methodDef;  
    BOOL isLastForeignExceptionFrame;  
} CorDebugExceptionObjectStackFrame;  
```  
  
## <a name="members"></a><span data-ttu-id="4b18e-105">Member</span><span class="sxs-lookup"><span data-stu-id="4b18e-105">Members</span></span>  
  
|<span data-ttu-id="4b18e-106">Member</span><span class="sxs-lookup"><span data-stu-id="4b18e-106">Member</span></span>|<span data-ttu-id="4b18e-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b18e-107">Description</span></span>|  
|------------|-----------------|  
|`pModule`|<span data-ttu-id="4b18e-108">Ein Zeiger auf das ICorDebugModule-Objekt für den aktuellen Frame.</span><span class="sxs-lookup"><span data-stu-id="4b18e-108">A pointer to the ICorDebugModule object for the current frame.</span></span>|  
|`ip`|<span data-ttu-id="4b18e-109">Der Wert des Anweisungszeigers (EIP/RIP) für den aktuellen Frame.</span><span class="sxs-lookup"><span data-stu-id="4b18e-109">The value of the instruction pointer (EIP/RIP) for the current frame.</span></span>|  
|`methodDef`|<span data-ttu-id="4b18e-110">Die Methodentoken für den aktuellen Frame.</span><span class="sxs-lookup"><span data-stu-id="4b18e-110">The method token for the current frame.</span></span>|  
|`isLastForeignExceptionFrame`|<span data-ttu-id="4b18e-111">Ein Wert, der angibt, ob die Rahmen der letzte Frame in einer fremden Ausnahme ist.</span><span class="sxs-lookup"><span data-stu-id="4b18e-111">A value that indicates whether the frame is the last frame in a foreign exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b18e-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4b18e-112">Remarks</span></span>  
 <span data-ttu-id="4b18e-113">Der Aufrufer muss die Zeiger auf das Objekt ICorDebugModule freigeben, sobald es nicht mehr verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4b18e-113">The caller must release the pointer to the ICorDebugModule object once it is no longer in use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b18e-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4b18e-114">Requirements</span></span>  
 <span data-ttu-id="4b18e-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b18e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b18e-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b18e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b18e-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b18e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b18e-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b18e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b18e-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b18e-119">See Also</span></span>  
 [<span data-ttu-id="4b18e-120">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="4b18e-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="4b18e-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="4b18e-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
