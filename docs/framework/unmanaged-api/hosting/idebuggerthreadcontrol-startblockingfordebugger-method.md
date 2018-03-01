---
title: IDebuggerThreadControl::StartBlockingForDebugger-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 99c0bc78705fa07883d92bf0cc1d90300c5ac549
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="c854d-102">IDebuggerThreadControl::StartBlockingForDebugger-Methode</span><span class="sxs-lookup"><span data-stu-id="c854d-102">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>
<span data-ttu-id="c854d-103">Benachrichtigt den Host, dass die Debugdienste sind im Begriff, starten die Blockierung aller Threads.</span><span class="sxs-lookup"><span data-stu-id="c854d-103">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c854d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c854d-104">Syntax</span></span>  
  
```  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c854d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c854d-105">Parameters</span></span>  
 `dwUnused`  
 <span data-ttu-id="c854d-106">[in] Für zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="c854d-106">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c854d-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c854d-107">Remarks</span></span>  
 <span data-ttu-id="c854d-108">Die `StartBlockingForDebugger` Methode kann in einem Runtime-Thread aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c854d-108">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c854d-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c854d-109">Requirements</span></span>  
 <span data-ttu-id="c854d-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c854d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c854d-111">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c854d-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c854d-112">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c854d-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c854d-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c854d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c854d-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c854d-114">See Also</span></span>  
 [<span data-ttu-id="c854d-115">IDebuggerThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c854d-115">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
