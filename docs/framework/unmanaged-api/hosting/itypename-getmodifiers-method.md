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
ms.openlocfilehash: c96764749a766f3b4bbff4cf6512677a47197f4c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095834"
---
# <a name="itypenamegetmodifiers-method"></a><span data-ttu-id="959c9-102">ITypeName::GetModifiers-Methode</span><span class="sxs-lookup"><span data-stu-id="959c9-102">ITypeName::GetModifiers Method</span></span>
<span data-ttu-id="959c9-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="959c9-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="959c9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="959c9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModifiers (  
    [in] DWORD           count,  
    [out] DWORD*         rgModifiers,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="959c9-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="959c9-105">Requirements</span></span>  
 <span data-ttu-id="959c9-106">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="959c9-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="959c9-107">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="959c9-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="959c9-108">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="959c9-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="959c9-109">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="959c9-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="959c9-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="959c9-110">See also</span></span>

- [<span data-ttu-id="959c9-111">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="959c9-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
