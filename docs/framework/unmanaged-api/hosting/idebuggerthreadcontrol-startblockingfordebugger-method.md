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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699902"
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="c9d1b-102">IDebuggerThreadControl::StartBlockingForDebugger-Methode</span><span class="sxs-lookup"><span data-stu-id="c9d1b-102">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>
<span data-ttu-id="c9d1b-103">Benachrichtigt den Host, dass die Debuggen von Diensten zu beginnen, alle Threads blockiert sind.</span><span class="sxs-lookup"><span data-stu-id="c9d1b-103">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9d1b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c9d1b-104">Syntax</span></span>  
  
```  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9d1b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c9d1b-105">Parameters</span></span>  
 `dwUnused`  
 <span data-ttu-id="c9d1b-106">[in] Für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="c9d1b-106">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9d1b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c9d1b-107">Remarks</span></span>  
 <span data-ttu-id="c9d1b-108">Die `StartBlockingForDebugger` Methode kann in einem Runtime-Thread aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c9d1b-108">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9d1b-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c9d1b-109">Requirements</span></span>  
 <span data-ttu-id="c9d1b-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9d1b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9d1b-111">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c9d1b-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c9d1b-112">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c9d1b-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c9d1b-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9d1b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9d1b-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9d1b-114">See also</span></span>

- [<span data-ttu-id="c9d1b-115">IDebuggerThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c9d1b-115">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
