---
title: ICorDebugManagedCallback2::CreateConnection-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.CreateConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::CreateConnection
helpviewer_keywords:
- CreateConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::CreateConnection method [.NET Framework debugging]
ms.assetid: 49e647be-9d63-4250-9d11-704e2a400d1b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f5035cd22ed099cec5e327c6957b13bcee52c766
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191123"
---
# <a name="icordebugmanagedcallback2createconnection-method"></a><span data-ttu-id="bca4b-102">ICorDebugManagedCallback2::CreateConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="bca4b-102">ICorDebugManagedCallback2::CreateConnection Method</span></span>
<span data-ttu-id="bca4b-103">Benachrichtigt den Debugger an, dass eine neue Verbindung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="bca4b-103">Notifies the debugger that a new connection has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bca4b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bca4b-104">Syntax</span></span>  
  
```  
HRESULT CreateConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId,  
    [in] WCHAR                *pConnName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bca4b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bca4b-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="bca4b-106">[in] Ein Zeiger auf ein "ICorDebugProcess"-Objekt, das den Prozess darstellt, in dem die Verbindung erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="bca4b-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the connection was created</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="bca4b-107">[in] Die ID der neuen Verbindung.</span><span class="sxs-lookup"><span data-stu-id="bca4b-107">[in] The ID of the new connection.</span></span>  
  
 `pConnName`  
 <span data-ttu-id="bca4b-108">[in] Ein Zeiger auf den Namen der neuen Verbindung.</span><span class="sxs-lookup"><span data-stu-id="bca4b-108">[in] A pointer to the name of the new connection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bca4b-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bca4b-109">Remarks</span></span>  
 <span data-ttu-id="bca4b-110">Ein `CreateConnection` Rückruf wird in den folgenden Fällen ausgelöst werden:</span><span class="sxs-lookup"><span data-stu-id="bca4b-110">A `CreateConnection` callback will be fired in either of the following cases:</span></span>  
  
-   <span data-ttu-id="bca4b-111">Wenn Fügt einen Debugger an einen Prozess aus, der Verbindungen enthält ein.</span><span class="sxs-lookup"><span data-stu-id="bca4b-111">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="bca4b-112">In diesem Fall die Laufzeit generiert und ein `CreateConnection` Ereignis und einem [ICorDebugManagedCallback2:: ChangeConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md) Ereignis für jede Verbindung im Prozess.</span><span class="sxs-lookup"><span data-stu-id="bca4b-112">In this case, the runtime will generate and dispatch a `CreateConnection` event and a [ICorDebugManagedCallback2::ChangeConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md) event for each connection in the process.</span></span>  
  
-   <span data-ttu-id="bca4b-113">Wenn ein Host ruft [ICLRDebugManager:: BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) in die [Hosting-API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="bca4b-113">When a host calls [ICLRDebugManager::BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bca4b-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bca4b-114">Requirements</span></span>  
 <span data-ttu-id="bca4b-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bca4b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bca4b-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bca4b-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bca4b-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bca4b-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="bca4b-118">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="bca4b-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bca4b-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bca4b-119">See also</span></span>

- [<span data-ttu-id="bca4b-120">ICorDebugManagedCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bca4b-120">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="bca4b-121">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bca4b-121">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
