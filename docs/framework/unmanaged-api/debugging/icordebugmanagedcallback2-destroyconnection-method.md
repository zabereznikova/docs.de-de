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
ms.openlocfilehash: d725cbe89e0631630affb6b0540a7d5f57ab6b89
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720112"
---
# <a name="icordebugmanagedcallback2destroyconnection-method"></a><span data-ttu-id="de74c-102">ICorDebugManagedCallback2::DestroyConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="de74c-102">ICorDebugManagedCallback2::DestroyConnection Method</span></span>

<span data-ttu-id="de74c-103">Benachrichtigt den Debugger, dass die angegebene Verbindung beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="de74c-103">Notifies the debugger that the specified connection has been terminated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de74c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="de74c-104">Syntax</span></span>  
  
```cpp  
HRESULT DestroyConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de74c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="de74c-105">Parameters</span></span>  

 `pProcess`  
 <span data-ttu-id="de74c-106">in Ein Zeiger auf ein ICorDebugProcess-Objekt, das den Prozess darstellt, der die zerstörte Verbindung enthält.</span><span class="sxs-lookup"><span data-stu-id="de74c-106">[in] A pointer to an ICorDebugProcess object that represents the process containing the connection that was destroyed.</span></span>  
  
 `dwConnectionId`  
 <span data-ttu-id="de74c-107">in Die ID der Verbindung, die zerstört wurde.</span><span class="sxs-lookup"><span data-stu-id="de74c-107">[in] The ID of the connection that was destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de74c-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="de74c-108">Remarks</span></span>  

 <span data-ttu-id="de74c-109">Ein `DestroyConnection` Rückruf wird ausgelöst, wenn ein Host [ICLRDebugManager:: EndConnection](../hosting/iclrdebugmanager-endconnection-method.md) in der [Hosting-API](../hosting/index.md)aufruft.</span><span class="sxs-lookup"><span data-stu-id="de74c-109">A `DestroyConnection` callback will be fired when a host calls [ICLRDebugManager::EndConnection](../hosting/iclrdebugmanager-endconnection-method.md) in the [Hosting API](../hosting/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de74c-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="de74c-110">Requirements</span></span>  

 <span data-ttu-id="de74c-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de74c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de74c-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de74c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de74c-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de74c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de74c-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de74c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de74c-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="de74c-115">See also</span></span>

- [<span data-ttu-id="de74c-116">ICorDebugManagedCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="de74c-116">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="de74c-117">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="de74c-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
