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
ms.openlocfilehash: e0183ed0f1556afb660ead042dd0d26a63ef75dd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133229"
---
# <a name="icorthreadpoolcorsetmaxthreads-method"></a><span data-ttu-id="cf6a4-102">ICorThreadpool::CorSetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="cf6a4-102">ICorThreadpool::CorSetMaxThreads Method</span></span>
<span data-ttu-id="cf6a4-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="cf6a4-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf6a4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cf6a4-104">Syntax</span></span>  
  
```cpp  
HRESULT CorSetMaxThreads (  
    [in] DWORD MaxWorkerThreads,  
    [in] DWORD MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="cf6a4-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cf6a4-105">Requirements</span></span>  
 <span data-ttu-id="cf6a4-106">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf6a4-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf6a4-107">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="cf6a4-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cf6a4-108">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="cf6a4-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cf6a4-109">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf6a4-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf6a4-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf6a4-110">See also</span></span>

- [<span data-ttu-id="cf6a4-111">ICorThreadpool-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cf6a4-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
