---
title: ICorThreadpool::CorQueueUserWorkItem-Methode
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorQueueUserWorkItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorQueueUserWorkItem
helpviewer_keywords:
- ICorThreadpool::CorQueueUserWorkItem method [.NET Framework hosting]
- CorQueueUserWorkItem method [.NET Framework hosting]
ms.assetid: 29ac7898-a7c7-433e-8f79-cd5237e0bab8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 249571cbe49fdce720630e31d2da1641aa979624
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218692"
---
# <a name="icorthreadpoolcorqueueuserworkitem-method"></a><span data-ttu-id="52f95-102">ICorThreadpool::CorQueueUserWorkItem-Methode</span><span class="sxs-lookup"><span data-stu-id="52f95-102">ICorThreadpool::CorQueueUserWorkItem Method</span></span>
<span data-ttu-id="52f95-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="52f95-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52f95-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="52f95-104">Syntax</span></span>  
  
```  
HRESULT CorQueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID                  Context,  
    [in] BOOL                   executeOnlyOnce,  
    [out] BOOL*                 result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="52f95-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="52f95-105">Requirements</span></span>  
 <span data-ttu-id="52f95-106">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52f95-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52f95-107">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="52f95-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="52f95-108">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="52f95-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="52f95-109">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="52f95-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="52f95-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52f95-110">See also</span></span>

- [<span data-ttu-id="52f95-111">ICorThreadpool-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="52f95-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
