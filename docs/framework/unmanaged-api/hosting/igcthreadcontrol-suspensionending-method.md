---
title: IGCThreadControl::SuspensionEnding-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCThreadControl.SuspensionEnding
api_location: mscoree.dll
api_type: COM
f1_keywords: SuspensionEnding
helpviewer_keywords:
- IGCThreadControl::SuspensionEnding method [.NET Framework hosting]
- SuspensionEnding method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 70814265-c734-4ddc-9502-fe8b28d2b414
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e4460d2b0eaf10d20ddd0c3641279a8ffc05c245
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="igcthreadcontrolsuspensionending-method"></a><span data-ttu-id="d67d0-102">IGCThreadControl::SuspensionEnding-Methode</span><span class="sxs-lookup"><span data-stu-id="d67d0-102">IGCThreadControl::SuspensionEnding Method</span></span>
<span data-ttu-id="d67d0-103">Benachrichtigt den Host an, dass die Laufzeit Threads nach einer Garbagecollection oder einer anderen Unterbrechung fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="d67d0-103">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d67d0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d67d0-104">Syntax</span></span>  
  
```  
HRESULT SuspensionEnding (  
    [in] DWORD Generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d67d0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d67d0-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="d67d0-106">[in] Die Generierung, für die eine Garbagecollection ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="d67d0-106">[in] The generation on which a garbage collection has been performed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d67d0-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d67d0-107">Remarks</span></span>  
 <span data-ttu-id="d67d0-108">Darf nicht verlegt werden alle Threads, die während der `SuspensionEnding` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="d67d0-108">Do not reschedule any threads during the `SuspensionEnding` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d67d0-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d67d0-109">Requirements</span></span>  
 <span data-ttu-id="d67d0-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d67d0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d67d0-111">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d67d0-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d67d0-112">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d67d0-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d67d0-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d67d0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d67d0-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d67d0-114">See Also</span></span>  
 [<span data-ttu-id="d67d0-115">IGCThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d67d0-115">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
