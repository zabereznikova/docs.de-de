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
ms.openlocfilehash: 3b1702c49fd88efff263121dd4b05c392dcb92f7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54496101"
---
# <a name="itypenamegetmodifiers-method"></a><span data-ttu-id="5cb52-102">ITypeName::GetModifiers-Methode</span><span class="sxs-lookup"><span data-stu-id="5cb52-102">ITypeName::GetModifiers Method</span></span>
<span data-ttu-id="5cb52-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="5cb52-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cb52-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5cb52-104">Syntax</span></span>  
  
```  
HRESULT GetModifiers (  
    [in] DWORD           count,  
    [out] DWORD*         rgModifiers,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="5cb52-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5cb52-105">Requirements</span></span>  
 <span data-ttu-id="5cb52-106">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5cb52-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cb52-107">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5cb52-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5cb52-108">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5cb52-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5cb52-109">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cb52-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cb52-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5cb52-110">See also</span></span>
- [<span data-ttu-id="5cb52-111">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5cb52-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
