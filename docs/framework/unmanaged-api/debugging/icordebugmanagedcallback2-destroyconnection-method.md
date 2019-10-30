---
title: ICorDebugManagedCallback2::DestroyConnection-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.DestroyConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::DestroyConnection
helpviewer_keywords:
- DestroyConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::DestroyConnection method [.NET Framework debugging]
ms.assetid: cf7940e9-4558-4319-925c-09f6c98c8fcd
topic_type:
- apiref
ms.openlocfilehash: a64df9f821021547efd08045e9f67fee25173e5a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137438"
---
# <a name="icordebugmanagedcallback2destroyconnection-method"></a><span data-ttu-id="8d6e7-102">ICorDebugManagedCallback2::DestroyConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="8d6e7-102">ICorDebugManagedCallback2::DestroyConnection Method</span></span>
<span data-ttu-id="8d6e7-103">Benachrichtigt den Debugger, dass die angegebene Verbindung beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="8d6e7-103">Notifies the debugger that the specified connection has been terminated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d6e7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8d6e7-104">Syntax</span></span>  
  
```cpp  
HRESULT DestroyConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d6e7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8d6e7-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="8d6e7-106">in Ein Zeiger auf ein ICorDebugProcess-Objekt, das den Prozess darstellt, der die zerstörte Verbindung enthält.</span><span class="sxs-lookup"><span data-stu-id="8d6e7-106">[in] A pointer to an ICorDebugProcess object that represents the process containing the connection that was destroyed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="8d6e7-107">in Die ID der Verbindung, die zerstört wurde.</span><span class="sxs-lookup"><span data-stu-id="8d6e7-107">[in] The ID of the connection that was destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d6e7-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8d6e7-108">Remarks</span></span>  
 <span data-ttu-id="8d6e7-109">Ein `DestroyConnection` Rückruf wird ausgelöst, wenn ein Host [ICLRDebugManager:: EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md) in der [Hosting-API](../../../../docs/framework/unmanaged-api/hosting/index.md)aufruft.</span><span class="sxs-lookup"><span data-stu-id="8d6e7-109">A `DestroyConnection` callback will be fired when a host calls [ICLRDebugManager::EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d6e7-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8d6e7-110">Requirements</span></span>  
 <span data-ttu-id="8d6e7-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d6e7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d6e7-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d6e7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d6e7-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d6e7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d6e7-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d6e7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d6e7-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8d6e7-115">See also</span></span>

- [<span data-ttu-id="8d6e7-116">ICorDebugManagedCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8d6e7-116">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="8d6e7-117">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8d6e7-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
