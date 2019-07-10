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
ms.openlocfilehash: abbfd21736d220f1cba029235c71a85bf3048ff0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761616"
---
# <a name="icordebugmanagedcallbacknamechange-method"></a><span data-ttu-id="f622e-102">ICorDebugManagedCallback::NameChange-Methode</span><span class="sxs-lookup"><span data-stu-id="f622e-102">ICorDebugManagedCallback::NameChange Method</span></span>
<span data-ttu-id="f622e-103">Benachrichtigt den Debugger, dass der Name einer Anwendungsdomäne oder einem Thread geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="f622e-103">Notifies the debugger that the name of either an application domain or a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f622e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f622e-104">Syntax</span></span>  
  
```cpp  
HRESULT NameChange (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f622e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f622e-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="f622e-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die entweder eine Namensänderung oder, enthält den Thread, der dessen Name geändert hat.</span><span class="sxs-lookup"><span data-stu-id="f622e-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that either had a name change or that contains the thread that had a name change.</span></span>  
  
 `pThread`  
 <span data-ttu-id="f622e-107">[in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt, der dessen Name geändert hat.</span><span class="sxs-lookup"><span data-stu-id="f622e-107">[in] A pointer to an ICorDebugThread object that represents the thread that had a name change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f622e-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f622e-108">Requirements</span></span>  
 <span data-ttu-id="f622e-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f622e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f622e-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f622e-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f622e-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f622e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f622e-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f622e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f622e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f622e-113">See also</span></span>

- [<span data-ttu-id="f622e-114">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f622e-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
