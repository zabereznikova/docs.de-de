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
ms.openlocfilehash: 8abe1b63aad7b73b3260553550112ded75b77bb9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54537737"
---
# <a name="icordebugmanagedcallbackexitthread-method"></a><span data-ttu-id="641b6-102">ICorDebugManagedCallback::ExitThread-Methode</span><span class="sxs-lookup"><span data-stu-id="641b6-102">ICorDebugManagedCallback::ExitThread Method</span></span>
<span data-ttu-id="641b6-103">Benachrichtigt den Debugger, dass ein Thread, der Ausführung von verwaltetem Code beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="641b6-103">Notifies the debugger that a thread that was executing managed code has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="641b6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="641b6-104">Syntax</span></span>  
  
```  
HRESULT ExitThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="641b6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="641b6-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="641b6-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne mit den verwalteten Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="641b6-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="641b6-107">[in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den verwalteten Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="641b6-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="641b6-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="641b6-108">Remarks</span></span>  
 <span data-ttu-id="641b6-109">Sobald die `ExitThread` Rückruf wird ausgelöst, der Thread wird in Threadenumerationen nicht mehr angezeigt.</span><span class="sxs-lookup"><span data-stu-id="641b6-109">Once the `ExitThread` callback is fired, the thread will no longer appear in thread enumerations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="641b6-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="641b6-110">Requirements</span></span>  
 <span data-ttu-id="641b6-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="641b6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="641b6-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="641b6-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="641b6-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="641b6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="641b6-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="641b6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="641b6-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="641b6-115">See also</span></span>
- [<span data-ttu-id="641b6-116">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="641b6-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
