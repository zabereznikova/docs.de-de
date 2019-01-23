---
title: ICorDebugValueBreakpoint-Schnittstelle1
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
ms.openlocfilehash: 58e6807b0546eadc4baacc276fa1ba7bda4e3aba
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54557759"
---
# <a name="icordebugvaluebreakpoint-interface1"></a><span data-ttu-id="a597f-102">ICorDebugValueBreakpoint-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="a597f-102">ICorDebugValueBreakpoint Interface1</span></span>
<span data-ttu-id="a597f-103">Erweitert die ICorDebugBreakpoint-Schnittstelle für den Zugriff auf bestimmte Werte.</span><span class="sxs-lookup"><span data-stu-id="a597f-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a597f-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="a597f-104">Methods</span></span>  
  
|<span data-ttu-id="a597f-105">Methode</span><span class="sxs-lookup"><span data-stu-id="a597f-105">Method</span></span>|<span data-ttu-id="a597f-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a597f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a597f-107">GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="a597f-107">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="a597f-108">Ruft einen Schnittstellenzeiger auf ein ICorDebugValue-Objekt, das den Wert des Objekts darstellt, auf denen der Haltepunkt gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="a597f-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a597f-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a597f-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a597f-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a597f-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a597f-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a597f-111">Requirements</span></span>  
 <span data-ttu-id="a597f-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a597f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a597f-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a597f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a597f-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a597f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a597f-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a597f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a597f-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a597f-116">See also</span></span>
- [<span data-ttu-id="a597f-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a597f-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
