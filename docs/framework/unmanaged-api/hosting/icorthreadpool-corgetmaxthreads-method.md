---
title: ICorThreadpool::CorGetMaxThreads-Methode
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
- ICorThreadpool.CorGetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGetMaxThreads
helpviewer_keywords:
- CorGetMaxThreads method [.NET Framework hosting]
- ICorThreadpool::CorGetMaxThreads method [.NET Framework hosting]
ms.assetid: 2861533a-cda0-47b3-b716-0d363505289b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 066497578f9587da670df5aede4750375c94a7ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorthreadpoolcorgetmaxthreads-method"></a><span data-ttu-id="42dd7-102">ICorThreadpool::CorGetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="42dd7-102">ICorThreadpool::CorGetMaxThreads Method</span></span>
<span data-ttu-id="42dd7-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="42dd7-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42dd7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="42dd7-104">Syntax</span></span>  
  
```  
HRESULT CorGetMaxThreads (  
    [out] DWORD *MaxWorkerThreads,  
    [out] DWORD *MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="42dd7-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="42dd7-105">Requirements</span></span>  
 <span data-ttu-id="42dd7-106">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42dd7-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42dd7-107">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="42dd7-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="42dd7-108">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="42dd7-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="42dd7-109">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42dd7-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42dd7-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42dd7-110">See Also</span></span>  
 [<span data-ttu-id="42dd7-111">ICorThreadpool-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="42dd7-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
