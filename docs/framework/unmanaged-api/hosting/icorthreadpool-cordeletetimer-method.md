---
title: ICorThreadpool::CorDeleteTimer-Methode
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorDeleteTimer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorDeleteTimer
helpviewer_keywords:
- ICorThreadpool::CorDeleteTimer method [.NET Framework hosting]
- CorDeleteTimer method [.NET Framework hosting]
ms.assetid: 74847c35-7ca1-466a-b750-b25e7b03d100
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 39142449ac7e03c629a834568ef469adffbf8dae
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757901"
---
# <a name="icorthreadpoolcordeletetimer-method"></a><span data-ttu-id="c24e6-102">ICorThreadpool::CorDeleteTimer-Methode</span><span class="sxs-lookup"><span data-stu-id="c24e6-102">ICorThreadpool::CorDeleteTimer Method</span></span>
<span data-ttu-id="c24e6-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="c24e6-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c24e6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c24e6-104">Syntax</span></span>  
  
```cpp  
HRESULT CorDeleteTimer (  
    [in]  HANDLE Timer,  
    [in]  HANDLE CompletionEvent,  
    [out] BOOL*  result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="c24e6-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c24e6-105">Requirements</span></span>  
 <span data-ttu-id="c24e6-106">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c24e6-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c24e6-107">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c24e6-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c24e6-108">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c24e6-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c24e6-109">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c24e6-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c24e6-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c24e6-110">See also</span></span>

- [<span data-ttu-id="c24e6-111">ICorThreadpool-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c24e6-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
