---
title: IGCThreadControl::SuspensionEnding-Methode
ms.date: 03/30/2017
api_name:
- IGCThreadControl.SuspensionEnding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SuspensionEnding
helpviewer_keywords:
- IGCThreadControl::SuspensionEnding method [.NET Framework hosting]
- SuspensionEnding method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 70814265-c734-4ddc-9502-fe8b28d2b414
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 90b0cba50129bc728089e41ece5a30697cfc3bc5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144416"
---
# <a name="igcthreadcontrolsuspensionending-method"></a><span data-ttu-id="6087a-102">IGCThreadControl::SuspensionEnding-Methode</span><span class="sxs-lookup"><span data-stu-id="6087a-102">IGCThreadControl::SuspensionEnding Method</span></span>
<span data-ttu-id="6087a-103">Benachrichtigt den Host, dass die Laufzeit Threads nach einer Garbagecollection oder einer anderen Unterbrechung fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="6087a-103">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6087a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6087a-104">Syntax</span></span>  
  
```  
HRESULT SuspensionEnding (  
    [in] DWORD Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6087a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6087a-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="6087a-106">[in] Die Objektgeneration, für die eine Garbagecollection durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="6087a-106">[in] The generation on which a garbage collection has been performed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6087a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6087a-107">Remarks</span></span>  
 <span data-ttu-id="6087a-108">Darf nicht verlegt werden alle Threads, während die `SuspensionEnding` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="6087a-108">Do not reschedule any threads during the `SuspensionEnding` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6087a-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6087a-109">Requirements</span></span>  
 <span data-ttu-id="6087a-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6087a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6087a-111">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6087a-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6087a-112">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6087a-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="6087a-113">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="6087a-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6087a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6087a-114">See also</span></span>

- [<span data-ttu-id="6087a-115">IGCThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6087a-115">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
