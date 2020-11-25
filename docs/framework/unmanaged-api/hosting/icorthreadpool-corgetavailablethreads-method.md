---
title: ICorThreadpool::CorGetAvailableThreads-Methode
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorGetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGetAvailableThreads
helpviewer_keywords:
- CorGetAvailableThreads method [.NET Framework hosting]
- ICorThreadpool::CorGetAvailableThreads method [.NET Framework hosting]
ms.assetid: 0b09b750-0b86-4ba4-9621-041857cfe8ba
topic_type:
- apiref
ms.openlocfilehash: 09b1f56600c05bf8e6028328adb80083b03ccc13
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725775"
---
# <a name="icorthreadpoolcorgetavailablethreads-method"></a><span data-ttu-id="97113-102">ICorThreadpool::CorGetAvailableThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="97113-102">ICorThreadpool::CorGetAvailableThreads Method</span></span>

<span data-ttu-id="97113-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="97113-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97113-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="97113-104">Syntax</span></span>  
  
```cpp  
HRESULT CorGetAvailableThreads (  
    [out] DWORD *AvailableWorkerThreads,  
    [out] DWORD *AvailableIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="97113-105">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="97113-105">Requirements</span></span>  

 <span data-ttu-id="97113-106">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97113-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97113-107">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="97113-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="97113-108">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="97113-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="97113-109">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97113-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97113-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="97113-110">See also</span></span>

- [<span data-ttu-id="97113-111">ICorThreadpool-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="97113-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
