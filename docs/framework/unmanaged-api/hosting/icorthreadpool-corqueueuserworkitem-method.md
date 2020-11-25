---
title: ICorThreadpool::CorQueueUserWorkItem-Methode
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorQueueUserWorkItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorQueueUserWorkItem
helpviewer_keywords:
- ICorThreadpool::CorQueueUserWorkItem method [.NET Framework hosting]
- CorQueueUserWorkItem method [.NET Framework hosting]
ms.assetid: 29ac7898-a7c7-433e-8f79-cd5237e0bab8
topic_type:
- apiref
ms.openlocfilehash: 42de7cd566db53e43985088851fd01fb66feabd9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720498"
---
# <a name="icorthreadpoolcorqueueuserworkitem-method"></a><span data-ttu-id="ed7f8-102">ICorThreadpool::CorQueueUserWorkItem-Methode</span><span class="sxs-lookup"><span data-stu-id="ed7f8-102">ICorThreadpool::CorQueueUserWorkItem Method</span></span>

<span data-ttu-id="ed7f8-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="ed7f8-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed7f8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ed7f8-104">Syntax</span></span>  
  
```cpp  
HRESULT CorQueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID                  Context,  
    [in] BOOL                   executeOnlyOnce,  
    [out] BOOL*                 result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="ed7f8-105">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ed7f8-105">Requirements</span></span>  

 <span data-ttu-id="ed7f8-106">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed7f8-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed7f8-107">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="ed7f8-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ed7f8-108">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ed7f8-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ed7f8-109">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed7f8-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed7f8-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ed7f8-110">See also</span></span>

- [<span data-ttu-id="ed7f8-111">ICorThreadpool-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ed7f8-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
