---
title: ICorRuntimeHost::SwitchOutLogicalThreadState-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorRuntimeHost.SwitchOutLogicalThreadState
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::SwitchOutLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchOutLogicalThreadState method [.NET Framework hosting]
- SwitchOutLogicalThreadState method [.NET Framework hosting]
ms.assetid: e1968f0b-2675-4dc2-8507-46164e1df154
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6302a836168f38991c7c371789d4913a3c95c16d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehostswitchoutlogicalthreadstate-method"></a><span data-ttu-id="1613b-102">ICorRuntimeHost::SwitchOutLogicalThreadState-Methode</span><span class="sxs-lookup"><span data-stu-id="1613b-102">ICorRuntimeHost::SwitchOutLogicalThreadState Method</span></span>
<span data-ttu-id="1613b-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="1613b-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1613b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1613b-104">Syntax</span></span>  
  
```  
HRESULT SwitchOutLogicalThreadState(  
    [out] DWORD **pFiberCookie  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1613b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1613b-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="1613b-106">[out] Cookie, der die Verbindungslinie, die ausgelagert wird angibt.</span><span class="sxs-lookup"><span data-stu-id="1613b-106">[out] Cookie that indicates the fiber being switched out.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1613b-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1613b-107">Requirements</span></span>  
 <span data-ttu-id="1613b-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1613b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1613b-109">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1613b-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1613b-110">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1613b-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1613b-111">**.NET Framework-Version:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="1613b-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1613b-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1613b-112">See Also</span></span>  
 [<span data-ttu-id="1613b-113">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1613b-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
