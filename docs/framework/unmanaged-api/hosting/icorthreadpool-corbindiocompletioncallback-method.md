---
title: ICorThreadpool::CorBindIoCompletionCallback-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5efd9811b0d5bfd16b802f0d504d69a4e7522833
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54707855"
---
# <a name="icorthreadpoolcorbindiocompletioncallback-method"></a><span data-ttu-id="5d5cf-102">ICorThreadpool::CorBindIoCompletionCallback-Methode</span><span class="sxs-lookup"><span data-stu-id="5d5cf-102">ICorThreadpool::CorBindIoCompletionCallback Method</span></span>
<span data-ttu-id="5d5cf-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="5d5cf-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d5cf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d5cf-104">Syntax</span></span>  
  
```  
HRESULT CorBindIoCompletionCallback (  
    [in] HANDLE                          fileHandle,  
    [in] LPOVERLAPPED_COMPLETION_ROUTINE callback  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="5d5cf-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5d5cf-105">Requirements</span></span>  
 <span data-ttu-id="5d5cf-106">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d5cf-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d5cf-107">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5d5cf-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5d5cf-108">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5d5cf-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5d5cf-109">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d5cf-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d5cf-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d5cf-110">See also</span></span>
- [<span data-ttu-id="5d5cf-111">ICorThreadpool-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5d5cf-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
