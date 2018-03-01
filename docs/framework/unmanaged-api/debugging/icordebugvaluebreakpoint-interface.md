---
title: ICorDebugValueBreakpoint Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugValueBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueBreakpoint
helpviewer_keywords:
- ICorDebugValueBreakpoint interface [.NET Framework debugging]
ms.assetid: c02338fe-da6c-467f-9567-70ebb387e901
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 92de5aa960c9ded27aef09d2c795437e9c599835
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvaluebreakpoint-interface1"></a><span data-ttu-id="e2ba0-102">ICorDebugValueBreakpoint Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="e2ba0-102">ICorDebugValueBreakpoint Interface1</span></span>
<span data-ttu-id="e2ba0-103">Erweitert die ICorDebugBreakpoint-Schnittstelle, um Zugriff auf bestimmte Werte zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="e2ba0-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e2ba0-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="e2ba0-104">Methods</span></span>  
  
|<span data-ttu-id="e2ba0-105">Methode</span><span class="sxs-lookup"><span data-stu-id="e2ba0-105">Method</span></span>|<span data-ttu-id="e2ba0-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e2ba0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e2ba0-107">GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="e2ba0-107">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="e2ba0-108">Ruft einen Schnittstellenzeiger auf ein ICorDebugValue-Objekt, das den Wert des Objekts darstellt, auf denen der Breakpoint festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="e2ba0-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2ba0-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e2ba0-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e2ba0-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e2ba0-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2ba0-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e2ba0-111">Requirements</span></span>  
 <span data-ttu-id="e2ba0-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2ba0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2ba0-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e2ba0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2ba0-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2ba0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2ba0-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2ba0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2ba0-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2ba0-116">See Also</span></span>  
 [<span data-ttu-id="e2ba0-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e2ba0-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
