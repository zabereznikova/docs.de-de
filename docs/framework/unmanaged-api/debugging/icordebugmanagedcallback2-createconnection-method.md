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
ms.openlocfilehash: 8e31f0a649fd1ca80d6557a0a7176549c67bf203
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501923"
---
# <a name="icordebugmanagedcallback2createconnection-method"></a><span data-ttu-id="7cfb6-102">ICorDebugManagedCallback2::CreateConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="7cfb6-102">ICorDebugManagedCallback2::CreateConnection Method</span></span>
<span data-ttu-id="7cfb6-103">Benachrichtigt den Debugger, dass eine neue Verbindung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7cfb6-103">Notifies the debugger that a new connection has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cfb6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7cfb6-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId,  
    [in] WCHAR                *pConnName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7cfb6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7cfb6-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="7cfb6-106">in Ein Zeiger auf ein ICorDebugProcess-Objekt, das den Prozess darstellt, in dem die Verbindung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7cfb6-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the connection was created</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="7cfb6-107">in Die ID der neuen Verbindung.</span><span class="sxs-lookup"><span data-stu-id="7cfb6-107">[in] The ID of the new connection.</span></span>  
  
 `pConnName`  
 <span data-ttu-id="7cfb6-108">in Ein Zeiger auf den Namen der neuen Verbindung.</span><span class="sxs-lookup"><span data-stu-id="7cfb6-108">[in] A pointer to the name of the new connection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7cfb6-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7cfb6-109">Remarks</span></span>  
 <span data-ttu-id="7cfb6-110">Ein `CreateConnection` Rückruf wird in einem der folgenden Fälle ausgelöst:</span><span class="sxs-lookup"><span data-stu-id="7cfb6-110">A `CreateConnection` callback will be fired in either of the following cases:</span></span>  
  
- <span data-ttu-id="7cfb6-111">Wenn ein Debugger an einen Prozess angefügt wird, der Verbindungen enthält.</span><span class="sxs-lookup"><span data-stu-id="7cfb6-111">When a debugger attaches to a process that contains connections.</span></span> <span data-ttu-id="7cfb6-112">In diesem Fall generiert und versendet die Laufzeit ein `CreateConnection` -Ereignis und ein [ICorDebugManagedCallback2:: ChangeConnection](icordebugmanagedcallback2-changeconnection-method.md) -Ereignis für jede Verbindung im Prozess.</span><span class="sxs-lookup"><span data-stu-id="7cfb6-112">In this case, the runtime will generate and dispatch a `CreateConnection` event and a [ICorDebugManagedCallback2::ChangeConnection](icordebugmanagedcallback2-changeconnection-method.md) event for each connection in the process.</span></span>  
  
- <span data-ttu-id="7cfb6-113">Wenn ein Host [ICLRDebugManager:: BeginConnection](../hosting/iclrdebugmanager-beginconnection-method.md) in der [Hosting-API](../hosting/index.md)aufruft.</span><span class="sxs-lookup"><span data-stu-id="7cfb6-113">When a host calls [ICLRDebugManager::BeginConnection](../hosting/iclrdebugmanager-beginconnection-method.md) in the [Hosting API](../hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cfb6-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7cfb6-114">Requirements</span></span>  
 <span data-ttu-id="7cfb6-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7cfb6-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cfb6-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7cfb6-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7cfb6-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7cfb6-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7cfb6-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cfb6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cfb6-119">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="7cfb6-119">See also</span></span>

- [<span data-ttu-id="7cfb6-120">ICorDebugManagedCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7cfb6-120">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="7cfb6-121">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7cfb6-121">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
