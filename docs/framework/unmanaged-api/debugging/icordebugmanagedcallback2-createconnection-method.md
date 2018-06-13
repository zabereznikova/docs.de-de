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
ms.openlocfilehash: d7024b8c0682b3351d185e518dd149737beb04bc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416357"
---
# <a name="icordebugmanagedcallback2createconnection-method"></a><span data-ttu-id="c7121-102">ICorDebugManagedCallback2::CreateConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="c7121-102">ICorDebugManagedCallback2::CreateConnection Method</span></span>
<span data-ttu-id="c7121-103">Benachrichtigt den Debugger an, dass eine neue Verbindung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c7121-103">Notifies the debugger that a new connection has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7121-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c7121-104">Syntax</span></span>  
  
```  
HRESULT CreateConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId,  
    [in] WCHAR                *pConnName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c7121-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c7121-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="c7121-106">[in] Ein Zeiger auf ein "ICorDebugProcess"-Objekt, das den Prozess darstellt, in dem die Verbindung erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="c7121-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the connection was created</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="c7121-107">[in] Die ID der neuen Verbindung.</span><span class="sxs-lookup"><span data-stu-id="c7121-107">[in] The ID of the new connection.</span></span>  
  
 `pConnName`  
 <span data-ttu-id="c7121-108">[in] Ein Zeiger auf den Namen der neuen Verbindung.</span><span class="sxs-lookup"><span data-stu-id="c7121-108">[in] A pointer to the name of the new connection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7121-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c7121-109">Remarks</span></span>  
 <span data-ttu-id="c7121-110">Ein `CreateConnection` Rückruf wird in den folgenden Fällen ausgelöst:</span><span class="sxs-lookup"><span data-stu-id="c7121-110">A `CreateConnection` callback will be fired in either of the following cases:</span></span>  
  
-   <span data-ttu-id="c7121-111">Wenn Fügt einen Debugger an einen Prozess, der Verbindungen enthält.</span><span class="sxs-lookup"><span data-stu-id="c7121-111">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="c7121-112">In diesem Fall die Laufzeit generiert und ein `CreateConnection` Ereignis und eine [ICorDebugManagedCallback2:: ChangeConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md) Ereignis für jede Verbindung im Prozess.</span><span class="sxs-lookup"><span data-stu-id="c7121-112">In this case, the runtime will generate and dispatch a `CreateConnection` event and a [ICorDebugManagedCallback2::ChangeConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md) event for each connection in the process.</span></span>  
  
-   <span data-ttu-id="c7121-113">Wenn ein Host ruft [ICLRDebugManager:: BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) in der [Hosting-API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span><span class="sxs-lookup"><span data-stu-id="c7121-113">When a host calls [ICLRDebugManager::BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) in the [Hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7121-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c7121-114">Requirements</span></span>  
 <span data-ttu-id="c7121-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7121-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7121-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c7121-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c7121-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7121-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7121-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7121-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7121-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7121-119">See Also</span></span>  
 [<span data-ttu-id="c7121-120">ICorDebugManagedCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c7121-120">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="c7121-121">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c7121-121">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
