---
title: ICorDebugManagedCallback::NameChange-Methode
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
- ICorDebugManagedCallback.NameChange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::NameChange
helpviewer_keywords:
- ICorDebugManagedCallback::NameChange method [.NET Framework debugging]
- NameChange method [.NET Framework debugging]
ms.assetid: a7018a0e-880e-4b68-b52a-1cd22c7aad62
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 31539413597c65b553794f07b1eeecdf3943f908
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbacknamechange-method"></a><span data-ttu-id="163bc-102">ICorDebugManagedCallback::NameChange-Methode</span><span class="sxs-lookup"><span data-stu-id="163bc-102">ICorDebugManagedCallback::NameChange Method</span></span>
<span data-ttu-id="163bc-103">Benachrichtigt den Debugger, dass der Name einer Anwendungsdomäne oder einem Thread geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="163bc-103">Notifies the debugger that the name of either an application domain or a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="163bc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="163bc-104">Syntax</span></span>  
  
```  
HRESULT NameChange (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="163bc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="163bc-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="163bc-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die entweder eine Namensänderung oder, mussten enthält den Thread, der dessen Name geändert hat.</span><span class="sxs-lookup"><span data-stu-id="163bc-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that either had a name change or that contains the thread that had a name change.</span></span>  
  
 `pThread`  
 <span data-ttu-id="163bc-107">[in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, der dessen Name geändert hat.</span><span class="sxs-lookup"><span data-stu-id="163bc-107">[in] A pointer to an ICorDebugThread object that represents the thread that had a name change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="163bc-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="163bc-108">Requirements</span></span>  
 <span data-ttu-id="163bc-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="163bc-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="163bc-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="163bc-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="163bc-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="163bc-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="163bc-112">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="163bc-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="163bc-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="163bc-113">See Also</span></span>  
 [<span data-ttu-id="163bc-114">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="163bc-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
