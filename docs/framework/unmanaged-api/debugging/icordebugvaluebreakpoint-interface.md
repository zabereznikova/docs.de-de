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
ms.openlocfilehash: f77268e069d322d0f491f78b154cf63b691e3e38
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966818"
---
# <a name="icordebugvaluebreakpoint-interface"></a><span data-ttu-id="a3a52-102">ICorDebugValueBreakpoint-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a3a52-102">ICorDebugValueBreakpoint Interface</span></span>
<span data-ttu-id="a3a52-103">Erweitert die icordebubreakpoint-Schnittstelle, um Zugriff auf bestimmte Werte bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="a3a52-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a3a52-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="a3a52-104">Methods</span></span>  
  
|<span data-ttu-id="a3a52-105">Methode</span><span class="sxs-lookup"><span data-stu-id="a3a52-105">Method</span></span>|<span data-ttu-id="a3a52-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a3a52-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a3a52-107">GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="a3a52-107">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="a3a52-108">Ruft einen Schnittstellen Zeiger auf ein icordebuvalue-Objekt ab, das den Wert des Objekts darstellt, für das der Breakpoint festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="a3a52-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3a52-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a3a52-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a3a52-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a3a52-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3a52-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a3a52-111">Requirements</span></span>  
 <span data-ttu-id="a3a52-112">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3a52-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3a52-113">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="a3a52-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a3a52-114">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3a52-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3a52-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3a52-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3a52-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3a52-116">See also</span></span>

- [<span data-ttu-id="a3a52-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a3a52-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
