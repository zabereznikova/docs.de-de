---
title: ICorDebugManagedCallback::Breakpoint-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Breakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Breakpoint
helpviewer_keywords:
- ICorDebugManagedCallback::Breakpoint method [.NET Framework debugging]
- Breakpoint method [.NET Framework debugging]
ms.assetid: 60b279b0-a726-46d2-8c53-76986a007ebb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 381fdecfb2cb194cd1eb00a5b55db6fb89eeebbc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmanagedcallbackbreakpoint-method"></a><span data-ttu-id="47cdd-102">ICorDebugManagedCallback::Breakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="47cdd-102">ICorDebugManagedCallback::Breakpoint Method</span></span>
<span data-ttu-id="47cdd-103">Benachrichtigt den Debugger an, wenn ein Breakpoint erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="47cdd-103">Notifies the debugger when a breakpoint is encountered.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47cdd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="47cdd-104">Syntax</span></span>  
  
```  
HRESULT Breakpoint (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="47cdd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="47cdd-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="47cdd-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die den Breakpoint enthält.</span><span class="sxs-lookup"><span data-stu-id="47cdd-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="47cdd-107">[in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, der den Breakpoint enthält.</span><span class="sxs-lookup"><span data-stu-id="47cdd-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="47cdd-108">[in] Ein Zeiger auf ein ICorDebugBreakpoint-Objekt, das den Haltepunkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="47cdd-108">[in] A pointer to an ICorDebugBreakpoint object that represents the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47cdd-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="47cdd-109">Requirements</span></span>  
 <span data-ttu-id="47cdd-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47cdd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47cdd-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="47cdd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="47cdd-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47cdd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47cdd-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47cdd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47cdd-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47cdd-114">See Also</span></span>  
 [<span data-ttu-id="47cdd-115">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="47cdd-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
