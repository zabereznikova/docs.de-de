---
title: ICorThreadpool::CorSetMaxThreads-Methode
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorSetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSetMaxThreads
helpviewer_keywords:
- ICorThreadpool::CorSetMaxThreads method [.NET Framework hosting]
- CorSetMaxThreads method [.NET Framework hosting]
ms.assetid: 4a846238-df4e-4060-ba3b-5173f6a51e85
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 48d84d5c45ea8e1af1da44480410692d46162810
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59198243"
---
# <a name="icorthreadpoolcorsetmaxthreads-method"></a><span data-ttu-id="a6504-102">ICorThreadpool::CorSetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="a6504-102">ICorThreadpool::CorSetMaxThreads Method</span></span>
<span data-ttu-id="a6504-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="a6504-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6504-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a6504-104">Syntax</span></span>  
  
```  
HRESULT CorSetMaxThreads (  
    [in] DWORD MaxWorkerThreads,  
    [in] DWORD MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="a6504-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a6504-105">Requirements</span></span>  
 <span data-ttu-id="a6504-106">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6504-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6504-107">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a6504-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a6504-108">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a6504-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="a6504-109">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="a6504-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a6504-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a6504-110">See also</span></span>

- [<span data-ttu-id="a6504-111">ICorThreadpool-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a6504-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
