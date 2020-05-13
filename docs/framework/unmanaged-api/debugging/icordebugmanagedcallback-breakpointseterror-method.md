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
ms.openlocfilehash: 0fa25dd33223ad2a9521aed0917ce35a2a33fa2f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213386"
---
# <a name="icordebugmanagedcallbackbreakpointseterror-method"></a><span data-ttu-id="4fa6d-102">ICorDebugManagedCallback::BreakpointSetError-Methode</span><span class="sxs-lookup"><span data-stu-id="4fa6d-102">ICorDebugManagedCallback::BreakpointSetError Method</span></span>
<span data-ttu-id="4fa6d-103">Benachrichtigt den Debugger, dass der Common Language Runtime einen Haltepunkt, der vor der JIT-Kompilierung (Just-in-Time) der Funktion festgelegt wurde, nicht genau binden konnte.</span><span class="sxs-lookup"><span data-stu-id="4fa6d-103">Notifies the debugger that the common language runtime was unable to accurately bind a breakpoint that was set before a function was just-in-time (JIT) compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fa6d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4fa6d-104">Syntax</span></span>  
  
```cpp  
HRESULT BreakpointSetError (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint,  
    [in] DWORD                dwError  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4fa6d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4fa6d-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="4fa6d-106">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die den ungebundenen Haltepunkt enthält.</span><span class="sxs-lookup"><span data-stu-id="4fa6d-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the unbound breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="4fa6d-107">in Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, der den ungebundenen Haltepunkt enthält.</span><span class="sxs-lookup"><span data-stu-id="4fa6d-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the unbound breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="4fa6d-108">in Ein Zeiger auf ein icordebubreakpoint-Objekt, das den ungebundenen Haltepunkt darstellt.</span><span class="sxs-lookup"><span data-stu-id="4fa6d-108">[in] A pointer to an ICorDebugBreakpoint object that represents the unbound breakpoint.</span></span>  
  
 `dwError`  
 <span data-ttu-id="4fa6d-109">in Eine ganze Zahl, die den Fehler angibt.</span><span class="sxs-lookup"><span data-stu-id="4fa6d-109">[in] An integer that indicates the error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4fa6d-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4fa6d-110">Remarks</span></span>  
 <span data-ttu-id="4fa6d-111">Der angegebene Haltepunkt wird nie gedrückt.</span><span class="sxs-lookup"><span data-stu-id="4fa6d-111">The given breakpoint will never be hit.</span></span> <span data-ttu-id="4fa6d-112">Der Debugger sollte ihn deaktivieren und erneut binden.</span><span class="sxs-lookup"><span data-stu-id="4fa6d-112">The debugger should deactivate and rebind it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fa6d-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4fa6d-113">Requirements</span></span>  
 <span data-ttu-id="4fa6d-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4fa6d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fa6d-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4fa6d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4fa6d-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4fa6d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4fa6d-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fa6d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fa6d-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4fa6d-118">See also</span></span>

- [<span data-ttu-id="4fa6d-119">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4fa6d-119">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
