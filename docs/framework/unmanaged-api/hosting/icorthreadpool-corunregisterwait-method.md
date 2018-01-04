---
title: ICorThreadpool::CorUnregisterWait-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorThreadpool.CorUnregisterWait
api_location: mscoree.dll
api_type: COM
f1_keywords: CorUnregisterWait
helpviewer_keywords:
- CorUnregisterWait method [.NET Framework hosting]
- ICorThreadpool::CorUnregisterWait method [.NET Framework hosting]
ms.assetid: 42c933f1-30a8-4011-bdea-e117f3c3265e
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fce6ac3f8ca571637127cb51282b3801c6d2b812
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorthreadpoolcorunregisterwait-method"></a><span data-ttu-id="9ac01-102">ICorThreadpool::CorUnregisterWait-Methode</span><span class="sxs-lookup"><span data-stu-id="9ac01-102">ICorThreadpool::CorUnregisterWait Method</span></span>
<span data-ttu-id="9ac01-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="9ac01-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ac01-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9ac01-104">Syntax</span></span>  
  
```  
HRESULT CorUnregisterWait (  
    [in] HANDLE hWaitObject,  
    [in] HANDLE CompletionEvent,  
    [out] BOOL* result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="9ac01-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9ac01-105">Requirements</span></span>  
 <span data-ttu-id="9ac01-106">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ac01-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ac01-107">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9ac01-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9ac01-108">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9ac01-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9ac01-109">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ac01-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ac01-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9ac01-110">See Also</span></span>  
 [<span data-ttu-id="9ac01-111">ICorThreadpool-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9ac01-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
