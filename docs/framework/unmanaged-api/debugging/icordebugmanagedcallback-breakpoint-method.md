---
title: ICorDebugManagedCallback::Breakpoint-Methode
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d7b0c521f1b2c5a2c258738239696ad48d4e9350
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackbreakpoint-method"></a><span data-ttu-id="63ac7-102">ICorDebugManagedCallback::Breakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="63ac7-102">ICorDebugManagedCallback::Breakpoint Method</span></span>
<span data-ttu-id="63ac7-103">Benachrichtigt den Debugger an, wenn ein Breakpoint erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="63ac7-103">Notifies the debugger when a breakpoint is encountered.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63ac7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="63ac7-104">Syntax</span></span>  
  
```  
HRESULT Breakpoint (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="63ac7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="63ac7-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="63ac7-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die den Breakpoint enthält.</span><span class="sxs-lookup"><span data-stu-id="63ac7-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="63ac7-107">[in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, der den Breakpoint enthält.</span><span class="sxs-lookup"><span data-stu-id="63ac7-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="63ac7-108">[in] Ein Zeiger auf ein ICorDebugBreakpoint-Objekt, das den Haltepunkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="63ac7-108">[in] A pointer to an ICorDebugBreakpoint object that represents the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63ac7-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="63ac7-109">Requirements</span></span>  
 <span data-ttu-id="63ac7-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63ac7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63ac7-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63ac7-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63ac7-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63ac7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63ac7-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63ac7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63ac7-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63ac7-114">See Also</span></span>  
 [<span data-ttu-id="63ac7-115">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="63ac7-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
