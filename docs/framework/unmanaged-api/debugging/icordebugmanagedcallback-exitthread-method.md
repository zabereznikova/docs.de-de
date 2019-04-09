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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37815d8aead1ec89826c13db6f012f2cd17bc792
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132443"
---
# <a name="icordebugmanagedcallbackexitthread-method"></a><span data-ttu-id="8f05a-102">ICorDebugManagedCallback::ExitThread-Methode</span><span class="sxs-lookup"><span data-stu-id="8f05a-102">ICorDebugManagedCallback::ExitThread Method</span></span>
<span data-ttu-id="8f05a-103">Benachrichtigt den Debugger, dass ein Thread, der Ausführung von verwaltetem Code beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="8f05a-103">Notifies the debugger that a thread that was executing managed code has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f05a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f05a-104">Syntax</span></span>  
  
```  
HRESULT ExitThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f05a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8f05a-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="8f05a-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne mit den verwalteten Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="8f05a-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="8f05a-107">[in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den verwalteten Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="8f05a-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f05a-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8f05a-108">Remarks</span></span>  
 <span data-ttu-id="8f05a-109">Sobald die `ExitThread` Rückruf wird ausgelöst, der Thread wird in Threadenumerationen nicht mehr angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8f05a-109">Once the `ExitThread` callback is fired, the thread will no longer appear in thread enumerations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f05a-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8f05a-110">Requirements</span></span>  
 <span data-ttu-id="8f05a-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f05a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f05a-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f05a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f05a-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f05a-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="8f05a-114">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="8f05a-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8f05a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f05a-115">See also</span></span>

- [<span data-ttu-id="8f05a-116">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8f05a-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
