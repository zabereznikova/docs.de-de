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
ms.openlocfilehash: 8591cb7f8eec3d92100b49db553ed1b5b6533c17
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59131073"
---
# <a name="icordebugmanagedcallbackbreakpoint-method"></a><span data-ttu-id="60d82-102">ICorDebugManagedCallback::Breakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="60d82-102">ICorDebugManagedCallback::Breakpoint Method</span></span>
<span data-ttu-id="60d82-103">Benachrichtigt den Debugger an, wenn ein Breakpoint erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="60d82-103">Notifies the debugger when a breakpoint is encountered.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60d82-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="60d82-104">Syntax</span></span>  
  
```  
HRESULT Breakpoint (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60d82-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="60d82-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="60d82-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die den Haltepunkt enthält.</span><span class="sxs-lookup"><span data-stu-id="60d82-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="60d82-107">[in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, der den Haltepunkt enthält.</span><span class="sxs-lookup"><span data-stu-id="60d82-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="60d82-108">[in] Ein Zeiger auf ein ICorDebugBreakpoint-Objekt, das den Haltepunkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="60d82-108">[in] A pointer to an ICorDebugBreakpoint object that represents the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60d82-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="60d82-109">Requirements</span></span>  
 <span data-ttu-id="60d82-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60d82-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60d82-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="60d82-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="60d82-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60d82-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60d82-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60d82-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60d82-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60d82-114">See also</span></span>

- [<span data-ttu-id="60d82-115">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="60d82-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
