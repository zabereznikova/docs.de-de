---
title: ICorThreadpool::CorGetAvailableThreads-Methode
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorGetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGetAvailableThreads
helpviewer_keywords:
- CorGetAvailableThreads method [.NET Framework hosting]
- ICorThreadpool::CorGetAvailableThreads method [.NET Framework hosting]
ms.assetid: 0b09b750-0b86-4ba4-9621-041857cfe8ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c929b9434507ea7cce936767f2ac72ff98fda7b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215793"
---
# <a name="icorthreadpoolcorgetavailablethreads-method"></a><span data-ttu-id="35acb-102">ICorThreadpool::CorGetAvailableThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="35acb-102">ICorThreadpool::CorGetAvailableThreads Method</span></span>
<span data-ttu-id="35acb-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="35acb-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35acb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="35acb-104">Syntax</span></span>  
  
```  
HRESULT CorGetAvailableThreads (  
    [out] DWORD *AvailableWorkerThreads,  
    [out] DWORD *AvailableIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="35acb-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="35acb-105">Requirements</span></span>  
 <span data-ttu-id="35acb-106">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35acb-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35acb-107">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="35acb-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="35acb-108">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="35acb-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="35acb-109">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="35acb-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="35acb-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35acb-110">See also</span></span>

- [<span data-ttu-id="35acb-111">ICorThreadpool-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="35acb-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
