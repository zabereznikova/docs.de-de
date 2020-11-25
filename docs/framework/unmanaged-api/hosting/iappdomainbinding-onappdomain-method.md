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
ms.openlocfilehash: 65f6be8c12ce057422ad178c759affed170e44ba
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721711"
---
# <a name="iappdomainbindingonappdomain-method"></a><span data-ttu-id="db9c6-102">IAppDomainBinding::OnAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="db9c6-102">IAppDomainBinding::OnAppDomain Method</span></span>

<span data-ttu-id="db9c6-103">Wird vom Common Language Runtime (CLR) aufgerufen, um den Host zu benachrichtigen, dass eine Anwendungsdomäne erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="db9c6-103">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db9c6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="db9c6-104">Syntax</span></span>  
  
```cpp  
HRESULT OnAppDomain (  
    [in] IUnknown* pAppdomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db9c6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="db9c6-105">Parameters</span></span>  

 `pAppdomain`  
 <span data-ttu-id="db9c6-106">in Ein Zeiger auf ein [IUnknown](/cpp/atl/iunknown) -Schnittstellen Objekt, das die neue Anwendungsdomäne darstellt.</span><span class="sxs-lookup"><span data-stu-id="db9c6-106">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) interface object that represents the new application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db9c6-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="db9c6-107">Requirements</span></span>  

 <span data-ttu-id="db9c6-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db9c6-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db9c6-109">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="db9c6-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="db9c6-110">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="db9c6-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="db9c6-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db9c6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db9c6-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="db9c6-112">See also</span></span>

- [<span data-ttu-id="db9c6-113">IAppDomainBinding-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="db9c6-113">IAppDomainBinding Interface</span></span>](iappdomainbinding-interface.md)
