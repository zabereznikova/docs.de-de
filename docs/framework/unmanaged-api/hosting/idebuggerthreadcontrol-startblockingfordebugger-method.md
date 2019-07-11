---
title: IDebuggerThreadControl::StartBlockingForDebugger-Methode
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.StartBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StartBlockingForDebugger
helpviewer_keywords:
- IDebuggerThreadControl::StartBlockingForDebugger method [.NET Framework hosting]
- StartBlockingForDebugger method [.NET Framework hosting]
ms.assetid: 5c8f11b4-35d3-4c39-9bbd-58b896ba5ba6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1cb314f2afce0cbbf1c5fb185f516a30ad8313af
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780519"
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="2fa68-102">IDebuggerThreadControl::StartBlockingForDebugger-Methode</span><span class="sxs-lookup"><span data-stu-id="2fa68-102">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>
<span data-ttu-id="2fa68-103">Benachrichtigt den Host, dass die Debuggen von Diensten zu beginnen, alle Threads blockiert sind.</span><span class="sxs-lookup"><span data-stu-id="2fa68-103">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fa68-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2fa68-104">Syntax</span></span>  
  
```cpp  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fa68-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2fa68-105">Parameters</span></span>  
 `dwUnused`  
 <span data-ttu-id="2fa68-106">[in] Für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="2fa68-106">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2fa68-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2fa68-107">Remarks</span></span>  
 <span data-ttu-id="2fa68-108">Die `StartBlockingForDebugger` Methode kann in einem Runtime-Thread aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2fa68-108">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fa68-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2fa68-109">Requirements</span></span>  
 <span data-ttu-id="2fa68-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2fa68-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fa68-111">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2fa68-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2fa68-112">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2fa68-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2fa68-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fa68-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fa68-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2fa68-114">See also</span></span>

- [<span data-ttu-id="2fa68-115">IDebuggerThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2fa68-115">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
