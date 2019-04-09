---
title: IAppDomainBinding::OnAppDomain-Methode
ms.date: 03/30/2017
api_name:
- IAppDomainBinding.OnAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- OnAppDomain
helpviewer_keywords:
- IAppDomainBinding::OnAppDomain method [.NET Framework hosting]
- OnAppDomain method [.NET Framework hosting]
ms.assetid: b419dcc9-e8aa-484b-af0d-0f40358edb99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2903395f5f834f2435b14d0b3f3e8bfe24af2867
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183052"
---
# <a name="iappdomainbindingonappdomain-method"></a><span data-ttu-id="c666c-102">IAppDomainBinding::OnAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="c666c-102">IAppDomainBinding::OnAppDomain Method</span></span>
<span data-ttu-id="c666c-103">Wird aufgerufen, von der common Language Runtime (CLR), um den Host zu benachrichtigen, dass eine Anwendungsdomäne erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c666c-103">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c666c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c666c-104">Syntax</span></span>  
  
```  
HRESULT OnAppDomain (  
    [in] IUnknown* pAppdomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c666c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c666c-105">Parameters</span></span>  
 `pAppdomain`  
 <span data-ttu-id="c666c-106">[in] Ein Zeiger auf ein [IUnknown](/cpp/atl/iunknown) Schnittstellenobjekt, das die neue Anwendungsdomäne darstellt.</span><span class="sxs-lookup"><span data-stu-id="c666c-106">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) interface object that represents the new application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c666c-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c666c-107">Requirements</span></span>  
 <span data-ttu-id="c666c-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c666c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c666c-109">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c666c-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c666c-110">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c666c-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="c666c-111">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="c666c-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c666c-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c666c-112">See also</span></span>

- [<span data-ttu-id="c666c-113">IAppDomainBinding-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c666c-113">IAppDomainBinding Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)
