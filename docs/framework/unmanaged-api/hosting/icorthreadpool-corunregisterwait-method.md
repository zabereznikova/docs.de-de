---
title: ICorThreadpool::CorUnregisterWait-Methode
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorUnregisterWait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorUnregisterWait
helpviewer_keywords:
- CorUnregisterWait method [.NET Framework hosting]
- ICorThreadpool::CorUnregisterWait method [.NET Framework hosting]
ms.assetid: 42c933f1-30a8-4011-bdea-e117f3c3265e
topic_type:
- apiref
ms.openlocfilehash: 431b90f8c5db5f40bf50be0b03fa315c6ea15ef7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133206"
---
# <a name="icorthreadpoolcorunregisterwait-method"></a><span data-ttu-id="9ae2e-102">ICorThreadpool::CorUnregisterWait-Methode</span><span class="sxs-lookup"><span data-stu-id="9ae2e-102">ICorThreadpool::CorUnregisterWait Method</span></span>
<span data-ttu-id="9ae2e-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="9ae2e-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ae2e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9ae2e-104">Syntax</span></span>  
  
```cpp  
HRESULT CorUnregisterWait (  
    [in] HANDLE hWaitObject,  
    [in] HANDLE CompletionEvent,  
    [out] BOOL* result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="9ae2e-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9ae2e-105">Requirements</span></span>  
 <span data-ttu-id="9ae2e-106">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ae2e-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ae2e-107">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="9ae2e-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9ae2e-108">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9ae2e-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9ae2e-109">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ae2e-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ae2e-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9ae2e-110">See also</span></span>

- [<span data-ttu-id="9ae2e-111">ICorThreadpool-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9ae2e-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
