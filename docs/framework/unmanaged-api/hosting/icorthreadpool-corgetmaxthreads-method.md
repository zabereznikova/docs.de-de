---
title: ICorThreadpool::CorGetMaxThreads-Methode
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorGetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGetMaxThreads
helpviewer_keywords:
- CorGetMaxThreads method [.NET Framework hosting]
- ICorThreadpool::CorGetMaxThreads method [.NET Framework hosting]
ms.assetid: 2861533a-cda0-47b3-b716-0d363505289b
topic_type:
- apiref
ms.openlocfilehash: 46ffdb21c1f3b501cc28afffc224349887af5644
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762748"
---
# <a name="icorthreadpoolcorgetmaxthreads-method"></a><span data-ttu-id="6f937-102">ICorThreadpool::CorGetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="6f937-102">ICorThreadpool::CorGetMaxThreads Method</span></span>
<span data-ttu-id="6f937-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="6f937-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f937-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f937-104">Syntax</span></span>  
  
```cpp  
HRESULT CorGetMaxThreads (  
    [out] DWORD *MaxWorkerThreads,  
    [out] DWORD *MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="6f937-105">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6f937-105">Requirements</span></span>  
 <span data-ttu-id="6f937-106">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f937-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f937-107">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="6f937-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6f937-108">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6f937-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6f937-109">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f937-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f937-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6f937-110">See also</span></span>

- [<span data-ttu-id="6f937-111">ICorThreadpool-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6f937-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
