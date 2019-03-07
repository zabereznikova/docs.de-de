---
title: ICorDebugManagedCallback::NameChange-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8bc4eb1895fe67c25354b42fe3ae1ffe80bca58
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491320"
---
# <a name="icordebugmanagedcallbacknamechange-method"></a><span data-ttu-id="2ca12-102">ICorDebugManagedCallback::NameChange-Methode</span><span class="sxs-lookup"><span data-stu-id="2ca12-102">ICorDebugManagedCallback::NameChange Method</span></span>
<span data-ttu-id="2ca12-103">Benachrichtigt den Debugger, dass der Name einer Anwendungsdomäne oder einem Thread geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="2ca12-103">Notifies the debugger that the name of either an application domain or a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ca12-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ca12-104">Syntax</span></span>  
  
```  
HRESULT NameChange (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ca12-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2ca12-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="2ca12-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die entweder eine Namensänderung oder, enthält den Thread, der dessen Name geändert hat.</span><span class="sxs-lookup"><span data-stu-id="2ca12-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that either had a name change or that contains the thread that had a name change.</span></span>  
  
 `pThread`  
 <span data-ttu-id="2ca12-107">[in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, der dessen Name geändert hat.</span><span class="sxs-lookup"><span data-stu-id="2ca12-107">[in] A pointer to an ICorDebugThread object that represents the thread that had a name change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ca12-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2ca12-108">Requirements</span></span>  
 <span data-ttu-id="2ca12-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ca12-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ca12-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ca12-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ca12-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ca12-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ca12-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ca12-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ca12-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ca12-113">See also</span></span>
- [<span data-ttu-id="2ca12-114">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2ca12-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
