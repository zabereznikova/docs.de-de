---
title: ICorDebugValueBreakpoint-Schnittstelle
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 778359a7d26b6e2f19984a1f7ff06a527f2449f0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993719"
---
# <a name="icordebugvaluebreakpoint-interface"></a><span data-ttu-id="9ab90-102">ICorDebugValueBreakpoint-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9ab90-102">ICorDebugValueBreakpoint Interface</span></span>
<span data-ttu-id="9ab90-103">Erweitert die ICorDebugBreakpoint-Schnittstelle für den Zugriff auf bestimmte Werte.</span><span class="sxs-lookup"><span data-stu-id="9ab90-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9ab90-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="9ab90-104">Methods</span></span>  
  
|<span data-ttu-id="9ab90-105">Methode</span><span class="sxs-lookup"><span data-stu-id="9ab90-105">Method</span></span>|<span data-ttu-id="9ab90-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9ab90-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9ab90-107">GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="9ab90-107">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="9ab90-108">Ruft einen Schnittstellenzeiger auf ein ICorDebugValue-Objekt, das den Wert des Objekts darstellt, auf denen der Haltepunkt gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="9ab90-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ab90-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9ab90-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ab90-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9ab90-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ab90-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9ab90-111">Requirements</span></span>  
 <span data-ttu-id="9ab90-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ab90-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ab90-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ab90-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ab90-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ab90-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ab90-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ab90-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ab90-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9ab90-116">See also</span></span>

- [<span data-ttu-id="9ab90-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9ab90-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
