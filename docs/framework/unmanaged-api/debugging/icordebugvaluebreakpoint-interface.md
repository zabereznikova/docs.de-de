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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59167745"
---
# <a name="icordebugvaluebreakpoint-interface"></a><span data-ttu-id="a071c-102">ICorDebugValueBreakpoint-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a071c-102">ICorDebugValueBreakpoint Interface</span></span>
<span data-ttu-id="a071c-103">Erweitert die ICorDebugBreakpoint-Schnittstelle für den Zugriff auf bestimmte Werte.</span><span class="sxs-lookup"><span data-stu-id="a071c-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a071c-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="a071c-104">Methods</span></span>  
  
|<span data-ttu-id="a071c-105">Methode</span><span class="sxs-lookup"><span data-stu-id="a071c-105">Method</span></span>|<span data-ttu-id="a071c-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a071c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a071c-107">GetValue-Methode</span><span class="sxs-lookup"><span data-stu-id="a071c-107">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="a071c-108">Ruft einen Schnittstellenzeiger auf ein ICorDebugValue-Objekt, das den Wert des Objekts darstellt, auf denen der Haltepunkt gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="a071c-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a071c-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a071c-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a071c-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a071c-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a071c-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a071c-111">Requirements</span></span>  
 <span data-ttu-id="a071c-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a071c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a071c-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a071c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a071c-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a071c-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a071c-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="a071c-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a071c-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a071c-116">See also</span></span>

- [<span data-ttu-id="a071c-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="a071c-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
