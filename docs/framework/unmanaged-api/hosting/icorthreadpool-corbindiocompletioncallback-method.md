---
title: ICorThreadpool::CorBindIoCompletionCallback-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorThreadpool.CorBindIoCompletionCallback
api_location: mscoree.dll
api_type: COM
f1_keywords: CorBindIoCompletionCallback
helpviewer_keywords:
- CorBindIoCompletionCallback method [.NET Framework hosting]
- ICorThreadpool::CorBindIoCompletionCallback method [.NET Framework hosting]
ms.assetid: 2b159225-f09c-42f1-aa7c-44087e121249
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 28baf49fd659564f1e1e356f52be6cd9cbb9f643
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorthreadpoolcorbindiocompletioncallback-method"></a><span data-ttu-id="63efd-102">ICorThreadpool::CorBindIoCompletionCallback-Methode</span><span class="sxs-lookup"><span data-stu-id="63efd-102">ICorThreadpool::CorBindIoCompletionCallback Method</span></span>
<span data-ttu-id="63efd-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="63efd-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63efd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="63efd-104">Syntax</span></span>  
  
```  
HRESULT CorBindIoCompletionCallback (  
    [in] HANDLE                          fileHandle,  
    [in] LPOVERLAPPED_COMPLETION_ROUTINE callback  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="63efd-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="63efd-105">Requirements</span></span>  
 <span data-ttu-id="63efd-106">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63efd-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63efd-107">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="63efd-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="63efd-108">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="63efd-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="63efd-109">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63efd-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63efd-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63efd-110">See Also</span></span>  
 [<span data-ttu-id="63efd-111">ICorThreadpool-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="63efd-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
