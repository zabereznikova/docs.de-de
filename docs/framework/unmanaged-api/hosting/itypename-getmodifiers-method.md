---
title: ITypeName::GetModifiers-Methode
ms.date: 03/30/2017
api_name:
- ITypeName.GetModifiers
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetModifiers
helpviewer_keywords:
- ITypeName::GetModifiers method [.NET Framework hosting]
- GetModifiers method [.NET Framework hosting]
ms.assetid: 75508c55-3e09-4135-80da-cc811003fa82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 78d86aff385bbff479c57d8902fbd0973a6ad1bc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59226416"
---
# <a name="itypenamegetmodifiers-method"></a><span data-ttu-id="2039c-102">ITypeName::GetModifiers-Methode</span><span class="sxs-lookup"><span data-stu-id="2039c-102">ITypeName::GetModifiers Method</span></span>
<span data-ttu-id="2039c-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="2039c-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2039c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2039c-104">Syntax</span></span>  
  
```  
HRESULT GetModifiers (  
    [in] DWORD           count,  
    [out] DWORD*         rgModifiers,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="2039c-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2039c-105">Requirements</span></span>  
 <span data-ttu-id="2039c-106">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2039c-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2039c-107">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2039c-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2039c-108">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2039c-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="2039c-109">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="2039c-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2039c-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2039c-110">See also</span></span>

- [<span data-ttu-id="2039c-111">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="2039c-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
