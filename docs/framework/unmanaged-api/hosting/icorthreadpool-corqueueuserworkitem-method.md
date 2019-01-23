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
ms.openlocfilehash: 6b13a2342510b48e72c7fd535cd085d0f50ca474
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534656"
---
# <a name="icorthreadpoolcorqueueuserworkitem-method"></a><span data-ttu-id="d1e0d-102">ICorThreadpool::CorQueueUserWorkItem-Methode</span><span class="sxs-lookup"><span data-stu-id="d1e0d-102">ICorThreadpool::CorQueueUserWorkItem Method</span></span>
<span data-ttu-id="d1e0d-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="d1e0d-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1e0d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d1e0d-104">Syntax</span></span>  
  
```  
HRESULT CorQueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID                  Context,  
    [in] BOOL                   executeOnlyOnce,  
    [out] BOOL*                 result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="d1e0d-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d1e0d-105">Requirements</span></span>  
 <span data-ttu-id="d1e0d-106">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1e0d-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1e0d-107">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d1e0d-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d1e0d-108">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d1e0d-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d1e0d-109">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1e0d-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1e0d-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1e0d-110">See also</span></span>
- [<span data-ttu-id="d1e0d-111">ICorThreadpool-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d1e0d-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
