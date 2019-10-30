---
title: ICorRuntimeHost::SwitchOutLogicalThreadState-Methode
ms.date: 03/30/2017
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
ms.openlocfilehash: 8151531e470b149012b2dd4fca918c8937f13918
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133342"
---
# <a name="icorruntimehostswitchoutlogicalthreadstate-method"></a><span data-ttu-id="c528a-102">ICorRuntimeHost::SwitchOutLogicalThreadState-Methode</span><span class="sxs-lookup"><span data-stu-id="c528a-102">ICorRuntimeHost::SwitchOutLogicalThreadState Method</span></span>
<span data-ttu-id="c528a-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="c528a-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c528a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c528a-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchOutLogicalThreadState(  
    [out] DWORD **pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c528a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c528a-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="c528a-106">vorgenommen Ein Cookie, das angibt, dass die Fiber ausgeschaltet wird.</span><span class="sxs-lookup"><span data-stu-id="c528a-106">[out] Cookie that indicates the fiber being switched out.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c528a-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c528a-107">Requirements</span></span>  
 <span data-ttu-id="c528a-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c528a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c528a-109">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="c528a-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c528a-110">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c528a-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c528a-111">**.NET Framework Version:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="c528a-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c528a-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c528a-112">See also</span></span>

- [<span data-ttu-id="c528a-113">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c528a-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
