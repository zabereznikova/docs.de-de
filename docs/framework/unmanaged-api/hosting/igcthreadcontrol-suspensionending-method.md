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
ms.openlocfilehash: d77380e35d8f5eee1e50b1030493e0b17cbadfba
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54713287"
---
# <a name="igcthreadcontrolsuspensionending-method"></a><span data-ttu-id="7df96-102">IGCThreadControl::SuspensionEnding-Methode</span><span class="sxs-lookup"><span data-stu-id="7df96-102">IGCThreadControl::SuspensionEnding Method</span></span>
<span data-ttu-id="7df96-103">Benachrichtigt den Host, dass die Laufzeit Threads nach einer Garbagecollection oder einer anderen Unterbrechung fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="7df96-103">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7df96-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7df96-104">Syntax</span></span>  
  
```  
HRESULT SuspensionEnding (  
    [in] DWORD Generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7df96-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7df96-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="7df96-106">[in] Die Objektgeneration, für die eine Garbagecollection durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="7df96-106">[in] The generation on which a garbage collection has been performed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7df96-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7df96-107">Remarks</span></span>  
 <span data-ttu-id="7df96-108">Darf nicht verlegt werden alle Threads, während die `SuspensionEnding` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="7df96-108">Do not reschedule any threads during the `SuspensionEnding` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7df96-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7df96-109">Requirements</span></span>  
 <span data-ttu-id="7df96-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7df96-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7df96-111">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7df96-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7df96-112">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7df96-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7df96-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7df96-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7df96-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7df96-114">See also</span></span>
- [<span data-ttu-id="7df96-115">IGCThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7df96-115">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
