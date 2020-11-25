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
ms.openlocfilehash: 38b3655da75750ffc3ea1c7983ce3b549d76f087
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733970"
---
# <a name="icorthreadpoolcorunregisterwait-method"></a><span data-ttu-id="dab36-102">ICorThreadpool::CorUnregisterWait-Methode</span><span class="sxs-lookup"><span data-stu-id="dab36-102">ICorThreadpool::CorUnregisterWait Method</span></span>

<span data-ttu-id="dab36-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="dab36-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dab36-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dab36-104">Syntax</span></span>  
  
```cpp  
HRESULT CorUnregisterWait (  
    [in] HANDLE hWaitObject,  
    [in] HANDLE CompletionEvent,  
    [out] BOOL* result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="dab36-105">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="dab36-105">Requirements</span></span>  

 <span data-ttu-id="dab36-106">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dab36-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dab36-107">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="dab36-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dab36-108">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="dab36-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dab36-109">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dab36-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dab36-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dab36-110">See also</span></span>

- [<span data-ttu-id="dab36-111">ICorThreadpool-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dab36-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
