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
ms.openlocfilehash: 8a4f7d4f422d80d044bcb92065dbefc7f421a069
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122606"
---
# <a name="icordebugmanagedcallbackbreakpoint-method"></a><span data-ttu-id="981c4-102">ICorDebugManagedCallback::Breakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="981c4-102">ICorDebugManagedCallback::Breakpoint Method</span></span>
<span data-ttu-id="981c4-103">Benachrichtigt den Debugger, wenn ein Breakpoint erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="981c4-103">Notifies the debugger when a breakpoint is encountered.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="981c4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="981c4-104">Syntax</span></span>  
  
```cpp  
HRESULT Breakpoint (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="981c4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="981c4-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="981c4-106">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die den Breakpoint enthält.</span><span class="sxs-lookup"><span data-stu-id="981c4-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="981c4-107">in Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, der den Breakpoint enthält.</span><span class="sxs-lookup"><span data-stu-id="981c4-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="981c4-108">in Ein Zeiger auf ein icordebubreakpoint-Objekt, das den Breakpoint darstellt.</span><span class="sxs-lookup"><span data-stu-id="981c4-108">[in] A pointer to an ICorDebugBreakpoint object that represents the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="981c4-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="981c4-109">Requirements</span></span>  
 <span data-ttu-id="981c4-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="981c4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="981c4-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="981c4-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="981c4-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="981c4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="981c4-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="981c4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="981c4-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="981c4-114">See also</span></span>

- [<span data-ttu-id="981c4-115">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="981c4-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
