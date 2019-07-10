---
title: ICorThreadpool::CorGetMaxThreads-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3699a761dfffa9a78e1acb5ea2a775a1386a9401
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751156"
---
# <a name="icorthreadpoolcorgetmaxthreads-method"></a><span data-ttu-id="fd473-102">ICorThreadpool::CorGetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="fd473-102">ICorThreadpool::CorGetMaxThreads Method</span></span>
<span data-ttu-id="fd473-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="fd473-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd473-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fd473-104">Syntax</span></span>  
  
```cpp  
HRESULT CorGetMaxThreads (  
    [out] DWORD *MaxWorkerThreads,  
    [out] DWORD *MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="fd473-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fd473-105">Requirements</span></span>  
 <span data-ttu-id="fd473-106">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd473-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd473-107">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fd473-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fd473-108">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fd473-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fd473-109">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd473-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd473-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd473-110">See also</span></span>

- [<span data-ttu-id="fd473-111">ICorThreadpool-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fd473-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
