---
title: ITypeName::GetTypeArguments-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4cd4fa8f4ba2bea5a2a853544eae6239bfaaeba
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132274"
---
# <a name="itypenamegettypearguments-method"></a><span data-ttu-id="77403-102">ITypeName::GetTypeArguments-Methode</span><span class="sxs-lookup"><span data-stu-id="77403-102">ITypeName::GetTypeArguments Method</span></span>
<span data-ttu-id="77403-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="77403-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77403-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="77403-104">Syntax</span></span>  
  
```  
HRESULT GetTypeArguments (  
    [in] DWORD           count,  
    [out] ITypeName**    rgpArguments,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="77403-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="77403-105">Requirements</span></span>  
 <span data-ttu-id="77403-106">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77403-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77403-107">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="77403-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="77403-108">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="77403-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="77403-109">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="77403-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="77403-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77403-110">See also</span></span>

- [<span data-ttu-id="77403-111">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="77403-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
