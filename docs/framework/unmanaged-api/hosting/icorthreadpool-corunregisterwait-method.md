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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c9ab5ca0a007422a2193d84a4915e2c0c67d855d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753188"
---
# <a name="icorthreadpoolcorunregisterwait-method"></a><span data-ttu-id="162ce-102">ICorThreadpool::CorUnregisterWait-Methode</span><span class="sxs-lookup"><span data-stu-id="162ce-102">ICorThreadpool::CorUnregisterWait Method</span></span>
<span data-ttu-id="162ce-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="162ce-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="162ce-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="162ce-104">Syntax</span></span>  
  
```cpp  
HRESULT CorUnregisterWait (  
    [in] HANDLE hWaitObject,  
    [in] HANDLE CompletionEvent,  
    [out] BOOL* result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="162ce-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="162ce-105">Requirements</span></span>  
 <span data-ttu-id="162ce-106">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="162ce-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="162ce-107">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="162ce-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="162ce-108">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="162ce-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="162ce-109">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="162ce-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="162ce-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="162ce-110">See also</span></span>

- [<span data-ttu-id="162ce-111">ICorThreadpool-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="162ce-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
