---
title: ICorThreadpool::CorBindIoCompletionCallback-Methode
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
- ICorThreadpool.CorBindIoCompletionCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorBindIoCompletionCallback
helpviewer_keywords:
- CorBindIoCompletionCallback method [.NET Framework hosting]
- ICorThreadpool::CorBindIoCompletionCallback method [.NET Framework hosting]
ms.assetid: 2b159225-f09c-42f1-aa7c-44087e121249
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 405fd52eb3354384c85049ab5230b08160144b09
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorthreadpoolcorbindiocompletioncallback-method"></a><span data-ttu-id="bd8bf-102">ICorThreadpool::CorBindIoCompletionCallback-Methode</span><span class="sxs-lookup"><span data-stu-id="bd8bf-102">ICorThreadpool::CorBindIoCompletionCallback Method</span></span>
<span data-ttu-id="bd8bf-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="bd8bf-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd8bf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bd8bf-104">Syntax</span></span>  
  
```  
HRESULT CorBindIoCompletionCallback (  
    [in] HANDLE                          fileHandle,  
    [in] LPOVERLAPPED_COMPLETION_ROUTINE callback  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="bd8bf-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bd8bf-105">Requirements</span></span>  
 <span data-ttu-id="bd8bf-106">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd8bf-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd8bf-107">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bd8bf-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bd8bf-108">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="bd8bf-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bd8bf-109">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd8bf-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd8bf-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd8bf-110">See Also</span></span>  
 [<span data-ttu-id="bd8bf-111">ICorThreadpool-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bd8bf-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
