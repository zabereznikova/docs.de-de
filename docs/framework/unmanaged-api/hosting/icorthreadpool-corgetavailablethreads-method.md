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
ms.openlocfilehash: 20b600eb50ca4992e20b991406d18a91feae5c54
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574454"
---
# <a name="icorthreadpoolcorgetavailablethreads-method"></a><span data-ttu-id="680b9-102">ICorThreadpool::CorGetAvailableThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="680b9-102">ICorThreadpool::CorGetAvailableThreads Method</span></span>
<span data-ttu-id="680b9-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="680b9-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="680b9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="680b9-104">Syntax</span></span>  
  
```  
HRESULT CorGetAvailableThreads (  
    [out] DWORD *AvailableWorkerThreads,  
    [out] DWORD *AvailableIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="680b9-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="680b9-105">Requirements</span></span>  
 <span data-ttu-id="680b9-106">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="680b9-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="680b9-107">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="680b9-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="680b9-108">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="680b9-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="680b9-109">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="680b9-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="680b9-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="680b9-110">See also</span></span>
- [<span data-ttu-id="680b9-111">ICorThreadpool-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="680b9-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
