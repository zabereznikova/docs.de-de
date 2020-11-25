---
title: ICorThreadpool::CorSetMaxThreads-Methode
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorSetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSetMaxThreads
helpviewer_keywords:
- ICorThreadpool::CorSetMaxThreads method [.NET Framework hosting]
- CorSetMaxThreads method [.NET Framework hosting]
ms.assetid: 4a846238-df4e-4060-ba3b-5173f6a51e85
topic_type:
- apiref
ms.openlocfilehash: f7d9d3d059abcf58fe0f4b35ce41046efb9c2400
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733983"
---
# <a name="icorthreadpoolcorsetmaxthreads-method"></a><span data-ttu-id="7ab0b-102">ICorThreadpool::CorSetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="7ab0b-102">ICorThreadpool::CorSetMaxThreads Method</span></span>

<span data-ttu-id="7ab0b-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="7ab0b-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ab0b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7ab0b-104">Syntax</span></span>  
  
```cpp  
HRESULT CorSetMaxThreads (  
    [in] DWORD MaxWorkerThreads,  
    [in] DWORD MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="7ab0b-105">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7ab0b-105">Requirements</span></span>  

 <span data-ttu-id="7ab0b-106">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ab0b-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ab0b-107">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="7ab0b-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7ab0b-108">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7ab0b-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7ab0b-109">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ab0b-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ab0b-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7ab0b-110">See also</span></span>

- [<span data-ttu-id="7ab0b-111">ICorThreadpool-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7ab0b-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
