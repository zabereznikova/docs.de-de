---
title: ICorConfiguration::SetGCThreadControl-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorConfiguration.SetGCThreadControl
api_location: mscoree.dll
api_type: COM
f1_keywords: SetGCThreadControl
helpviewer_keywords:
- ICorConfiguration::SetGCThreadControl method [.NET Framework hosting]
- SetGCThreadControl method [.NET Framework hosting]
ms.assetid: 72e38e61-3d56-4ae3-b8f6-0ab7922aaf11
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6b6b28b67f924df4d7f587d0364bce2a853f60b7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a><span data-ttu-id="c2024-102">ICorConfiguration::SetGCThreadControl-Methode</span><span class="sxs-lookup"><span data-stu-id="c2024-102">ICorConfiguration::SetGCThreadControl Method</span></span>
<span data-ttu-id="c2024-103">Legt die Rückrufschnittstelle für die Planung von Threads für nicht-Runtime-Aufgaben, die andernfalls für eine Garbagecollection blockiert werden würde.</span><span class="sxs-lookup"><span data-stu-id="c2024-103">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2024-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c2024-104">Syntax</span></span>  
  
```  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c2024-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c2024-105">Parameters</span></span>  
 `pGCThreadControl`  
 <span data-ttu-id="c2024-106">[in] Ein Zeiger auf ein [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md) -Objekt, das den Host über das Anhalten des Threads für Laufzeitaufgaben benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="c2024-106">[in] A pointer to an [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md) object that notifies the host about the suspension of threads for non-runtime tasks.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2024-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c2024-107">Remarks</span></span>  
 <span data-ttu-id="c2024-108">Der Host kann wählen, in der [IGCThreadControl:: ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md) Rückruf an, ob ein Thread verlegt.</span><span class="sxs-lookup"><span data-stu-id="c2024-108">The host may choose within the [IGCThreadControl::ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md) callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2024-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c2024-109">Requirements</span></span>  
 <span data-ttu-id="c2024-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2024-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2024-111">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c2024-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c2024-112">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c2024-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c2024-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2024-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2024-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2024-114">See Also</span></span>  
 [<span data-ttu-id="c2024-115">ICorConfiguration-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c2024-115">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
