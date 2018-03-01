---
title: ITypeName::GetTypeArguments-Methode
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
- ITypeName.GetTypeArguments
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetTypeArguments
helpviewer_keywords:
- ITypeName::GetTypeArguments method [.NET Framework hosting]
- GetTypeArguments method [.NET Framework hosting]
ms.assetid: 638d77df-ff9c-40d9-88ee-930f5f87ada1
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7b0110d67b5f72a060fae3800ca6292465896e3a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="itypenamegettypearguments-method"></a><span data-ttu-id="2d1e3-102">ITypeName::GetTypeArguments-Methode</span><span class="sxs-lookup"><span data-stu-id="2d1e3-102">ITypeName::GetTypeArguments Method</span></span>
<span data-ttu-id="2d1e3-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="2d1e3-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d1e3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d1e3-104">Syntax</span></span>  
  
```  
HRESULT GetTypeArguments (  
    [in] DWORD           count,  
    [out] ITypeName**    rgpArguments,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="2d1e3-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2d1e3-105">Requirements</span></span>  
 <span data-ttu-id="2d1e3-106">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d1e3-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d1e3-107">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2d1e3-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2d1e3-108">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2d1e3-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2d1e3-109">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d1e3-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d1e3-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d1e3-110">See Also</span></span>  
 [<span data-ttu-id="2d1e3-111">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="2d1e3-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
