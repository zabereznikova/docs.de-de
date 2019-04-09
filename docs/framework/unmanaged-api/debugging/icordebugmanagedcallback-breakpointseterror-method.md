---
title: ICorDebugManagedCallback::BreakpointSetError-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.BreakpointSetError
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::BreakpointSetError
helpviewer_keywords:
- BreakpointSetError method [.NET Framework debugging]
- ICorDebugManagedCallback::BreakpointSetError method [.NET Framework debugging]
ms.assetid: f2b773a4-c4d0-429c-9717-51d6e2ed86af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 27d5b8e0127971cc3a46560590fd9d95f0ffd1f0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59151020"
---
# <a name="icordebugmanagedcallbackbreakpointseterror-method"></a><span data-ttu-id="979d1-102">ICorDebugManagedCallback::BreakpointSetError-Methode</span><span class="sxs-lookup"><span data-stu-id="979d1-102">ICorDebugManagedCallback::BreakpointSetError Method</span></span>
<span data-ttu-id="979d1-103">Benachrichtigt den Debugger, dass die common Language Runtime nicht genau einen Haltepunkt zu binden, der festgelegt wurde, bevor eine Funktion just-in-Time (JIT) kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="979d1-103">Notifies the debugger that the common language runtime was unable to accurately bind a breakpoint that was set before a function was just-in-time (JIT) compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="979d1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="979d1-104">Syntax</span></span>  
  
```  
HRESULT BreakpointSetError (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint,  
    [in] DWORD                dwError  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="979d1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="979d1-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="979d1-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die nicht gebundenen Haltepunkt enthält.</span><span class="sxs-lookup"><span data-stu-id="979d1-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the unbound breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="979d1-107">[in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, der den ungebundenen Haltepunkt enthält.</span><span class="sxs-lookup"><span data-stu-id="979d1-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the unbound breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="979d1-108">[in] Ein Zeiger auf ein ICorDebugBreakpoint-Objekt, das den ungebundenen Haltepunkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="979d1-108">[in] A pointer to an ICorDebugBreakpoint object that represents the unbound breakpoint.</span></span>  
  
 `dwError`  
 <span data-ttu-id="979d1-109">[in] Eine ganze Zahl, die den Fehler angibt.</span><span class="sxs-lookup"><span data-stu-id="979d1-109">[in] An integer that indicates the error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="979d1-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="979d1-110">Remarks</span></span>  
 <span data-ttu-id="979d1-111">Der angegebene Haltepunkt wird niemals erreicht werden.</span><span class="sxs-lookup"><span data-stu-id="979d1-111">The given breakpoint will never be hit.</span></span> <span data-ttu-id="979d1-112">Der Debugger sollte deaktivieren und binden Sie es erneut.</span><span class="sxs-lookup"><span data-stu-id="979d1-112">The debugger should deactivate and rebind it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="979d1-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="979d1-113">Requirements</span></span>  
 <span data-ttu-id="979d1-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="979d1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="979d1-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="979d1-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="979d1-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="979d1-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="979d1-117">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="979d1-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="979d1-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="979d1-118">See also</span></span>

- [<span data-ttu-id="979d1-119">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="979d1-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
