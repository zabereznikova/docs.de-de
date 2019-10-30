---
title: ICorRuntimeHost::SwitchInLogicalThreadState-Methode
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.SwitchInLogicalThreadState
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState method [.NET Framework hosting]
- SwitchInLogicalThreadState method [.NET Framework hosting]
ms.assetid: 7df1e492-8014-43ea-80d1-a4743e9b1c17
topic_type:
- apiref
ms.openlocfilehash: b6569b5dab89a88a24cf2dfc873da9740e5af505
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133378"
---
# <a name="icorruntimehostswitchinlogicalthreadstate-method"></a><span data-ttu-id="c2b82-102">ICorRuntimeHost::SwitchInLogicalThreadState-Methode</span><span class="sxs-lookup"><span data-stu-id="c2b82-102">ICorRuntimeHost::SwitchInLogicalThreadState Method</span></span>
<span data-ttu-id="c2b82-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="c2b82-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2b82-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c2b82-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchInLogicalThreadState(  
    [in] DWORD *pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2b82-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c2b82-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="c2b82-106">in Ein Cookie, das die zu verwendende Fiber angibt.</span><span class="sxs-lookup"><span data-stu-id="c2b82-106">[in] Cookie that indicates the fiber to use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2b82-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c2b82-107">Requirements</span></span>  
 <span data-ttu-id="c2b82-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2b82-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2b82-109">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="c2b82-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c2b82-110">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c2b82-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c2b82-111">**.NET Framework Version:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="c2b82-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2b82-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2b82-112">See also</span></span>

- [<span data-ttu-id="c2b82-113">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c2b82-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
