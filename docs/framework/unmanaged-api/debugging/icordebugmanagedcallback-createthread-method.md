---
title: ICorDebugManagedCallback::CreateThread-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.CreateThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateThread method
helpviewer_keywords:
- ICorDebugManagedCallback::CreateThread method [.NET Framework debugging]
- CreateThread method [.NET Framework debugging]
ms.assetid: 6b961728-21c4-4e8d-ae81-197458be62f4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9721d88c8ce138b19c98f113d9eb034c5e1c55dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmanagedcallbackcreatethread-method"></a><span data-ttu-id="9d341-102">ICorDebugManagedCallback::CreateThread-Methode</span><span class="sxs-lookup"><span data-stu-id="9d341-102">ICorDebugManagedCallback::CreateThread Method</span></span>
<span data-ttu-id="9d341-103">Benachrichtigt den Debugger, dass eine Threadausführung begonnen hat, verwalteten Code ausführt.</span><span class="sxs-lookup"><span data-stu-id="9d341-103">Notifies the debugger that a thread has started executing managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d341-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9d341-104">Syntax</span></span>  
  
```  
HRESULT CreateThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9d341-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9d341-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="9d341-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die den Thread enthält.</span><span class="sxs-lookup"><span data-stu-id="9d341-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="9d341-107">[in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="9d341-107">[in] A pointer to an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d341-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9d341-108">Remarks</span></span>  
 <span data-ttu-id="9d341-109">Der Thread wird bei der ersten verwalteten Code-Anweisung auszuführende positioniert werden.</span><span class="sxs-lookup"><span data-stu-id="9d341-109">The thread will be positioned at the first managed code instruction to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d341-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9d341-110">Requirements</span></span>  
 <span data-ttu-id="9d341-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d341-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d341-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d341-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d341-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d341-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d341-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d341-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d341-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d341-115">See Also</span></span>  
 [<span data-ttu-id="9d341-116">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9d341-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
