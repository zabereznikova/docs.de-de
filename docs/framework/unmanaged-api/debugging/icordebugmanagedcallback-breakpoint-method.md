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
ms.openlocfilehash: ac91a9c662a82c5ab870d01cb4b5d87c7af6b6ba
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782071"
---
# <a name="icordebugmanagedcallbackbreakpoint-method"></a><span data-ttu-id="9a8da-102">ICorDebugManagedCallback::Breakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="9a8da-102">ICorDebugManagedCallback::Breakpoint Method</span></span>
<span data-ttu-id="9a8da-103">Benachrichtigt den Debugger, wenn ein Breakpoint erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="9a8da-103">Notifies the debugger when a breakpoint is encountered.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a8da-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9a8da-104">Syntax</span></span>  
  
```cpp  
HRESULT Breakpoint (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a8da-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="9a8da-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="9a8da-106">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die den Breakpoint enthält.</span><span class="sxs-lookup"><span data-stu-id="9a8da-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="9a8da-107">in Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, der den Breakpoint enthält.</span><span class="sxs-lookup"><span data-stu-id="9a8da-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="9a8da-108">in Ein Zeiger auf ein icordebubreakpoint-Objekt, das den Breakpoint darstellt.</span><span class="sxs-lookup"><span data-stu-id="9a8da-108">[in] A pointer to an ICorDebugBreakpoint object that represents the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a8da-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9a8da-109">Requirements</span></span>  
 <span data-ttu-id="9a8da-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a8da-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a8da-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a8da-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a8da-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a8da-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a8da-113">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a8da-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a8da-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a8da-114">See also</span></span>

- [<span data-ttu-id="9a8da-115">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9a8da-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
