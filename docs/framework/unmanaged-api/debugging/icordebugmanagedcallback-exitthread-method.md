---
title: ICorDebugManagedCallback::ExitThread-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitThread
helpviewer_keywords:
- ExitThread method [.NET Framework debugging]
- ICorDebugManagedCallback::ExitThread method [.NET Framework debugging]
ms.assetid: 62db708b-6cf0-45c5-b897-4b5c75bd2505
topic_type:
- apiref
ms.openlocfilehash: 3ba1280aa44a9445f6af7fe9a8769b7cdc7edb66
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205244"
---
# <a name="icordebugmanagedcallbackexitthread-method"></a><span data-ttu-id="131f9-102">ICorDebugManagedCallback::ExitThread-Methode</span><span class="sxs-lookup"><span data-stu-id="131f9-102">ICorDebugManagedCallback::ExitThread Method</span></span>
<span data-ttu-id="131f9-103">Benachrichtigt den Debugger, dass ein Thread, der verwalteten Code ausgeführt hat, beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="131f9-103">Notifies the debugger that a thread that was executing managed code has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="131f9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="131f9-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="131f9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="131f9-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="131f9-106">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die den verwalteten Thread enthält.</span><span class="sxs-lookup"><span data-stu-id="131f9-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="131f9-107">in Ein Zeiger auf ein ICorDebugThread-Objekt, das den verwalteten Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="131f9-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="131f9-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="131f9-108">Remarks</span></span>  
 <span data-ttu-id="131f9-109">Nachdem der `ExitThread` Rückruf ausgelöst wurde, wird der Thread nicht mehr in Thread Enumerationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="131f9-109">Once the `ExitThread` callback is fired, the thread will no longer appear in thread enumerations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="131f9-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="131f9-110">Requirements</span></span>  
 <span data-ttu-id="131f9-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="131f9-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="131f9-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="131f9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="131f9-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="131f9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="131f9-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="131f9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="131f9-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="131f9-115">See also</span></span>

- [<span data-ttu-id="131f9-116">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="131f9-116">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
