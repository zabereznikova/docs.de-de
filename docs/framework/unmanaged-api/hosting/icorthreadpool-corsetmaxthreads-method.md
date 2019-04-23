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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 48d84d5c45ea8e1af1da44480410692d46162810
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59198243"
---
# <a name="icorthreadpoolcorsetmaxthreads-method"></a><span data-ttu-id="f8674-102">ICorThreadpool::CorSetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="f8674-102">ICorThreadpool::CorSetMaxThreads Method</span></span>
<span data-ttu-id="f8674-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="f8674-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8674-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f8674-104">Syntax</span></span>  
  
```  
HRESULT CorSetMaxThreads (  
    [in] DWORD MaxWorkerThreads,  
    [in] DWORD MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="f8674-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f8674-105">Requirements</span></span>  
 <span data-ttu-id="f8674-106">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8674-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8674-107">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f8674-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f8674-108">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f8674-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f8674-109">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8674-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8674-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8674-110">See also</span></span>

- [<span data-ttu-id="f8674-111">ICorThreadpool-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8674-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
