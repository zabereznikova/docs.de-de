---
title: ICorDebugManagedCallback::ExitThread-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.ExitThread
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::ExitThread
helpviewer_keywords:
- ExitThread method [.NET Framework debugging]
- ICorDebugManagedCallback::ExitThread method [.NET Framework debugging]
ms.assetid: 62db708b-6cf0-45c5-b897-4b5c75bd2505
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6c39a8c92a8c0be8d0607663a833ac7307ca26d3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackexitthread-method"></a><span data-ttu-id="ba6c3-102">ICorDebugManagedCallback::ExitThread-Methode</span><span class="sxs-lookup"><span data-stu-id="ba6c3-102">ICorDebugManagedCallback::ExitThread Method</span></span>
<span data-ttu-id="ba6c3-103">Benachrichtigt den Debugger an, ein Thread, der verwalteten Code ausführt, wurde beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-103">Notifies the debugger that a thread that was executing managed code has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba6c3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ba6c3-104">Syntax</span></span>  
  
```  
HRESULT ExitThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ba6c3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ba6c3-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="ba6c3-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne mit den verwalteten Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="ba6c3-107">[in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den verwalteten Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba6c3-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ba6c3-108">Remarks</span></span>  
 <span data-ttu-id="ba6c3-109">Sobald die `ExitThread` Rückruf ausgelöst wird, der Thread wird im Threadenumerationen nicht mehr angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ba6c3-109">Once the `ExitThread` callback is fired, the thread will no longer appear in thread enumerations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba6c3-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ba6c3-110">Requirements</span></span>  
 <span data-ttu-id="ba6c3-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba6c3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba6c3-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ba6c3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ba6c3-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba6c3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba6c3-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba6c3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba6c3-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba6c3-115">See Also</span></span>  
 [<span data-ttu-id="ba6c3-116">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ba6c3-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
