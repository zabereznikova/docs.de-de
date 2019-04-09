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
ms.openlocfilehash: dfc94c2de1a14842cc017e5c4ef6023154c20f2a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59194031"
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="cf9e5-102">IDebuggerThreadControl::StartBlockingForDebugger-Methode</span><span class="sxs-lookup"><span data-stu-id="cf9e5-102">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>
<span data-ttu-id="cf9e5-103">Benachrichtigt den Host, dass die Debuggen von Diensten zu beginnen, alle Threads blockiert sind.</span><span class="sxs-lookup"><span data-stu-id="cf9e5-103">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf9e5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cf9e5-104">Syntax</span></span>  
  
```  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf9e5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cf9e5-105">Parameters</span></span>  
 `dwUnused`  
 <span data-ttu-id="cf9e5-106">[in] Für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="cf9e5-106">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf9e5-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cf9e5-107">Remarks</span></span>  
 <span data-ttu-id="cf9e5-108">Die `StartBlockingForDebugger` Methode kann in einem Runtime-Thread aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="cf9e5-108">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf9e5-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cf9e5-109">Requirements</span></span>  
 <span data-ttu-id="cf9e5-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf9e5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf9e5-111">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cf9e5-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cf9e5-112">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="cf9e5-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="cf9e5-113">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="cf9e5-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cf9e5-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf9e5-114">See also</span></span>

- [<span data-ttu-id="cf9e5-115">IDebuggerThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cf9e5-115">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
