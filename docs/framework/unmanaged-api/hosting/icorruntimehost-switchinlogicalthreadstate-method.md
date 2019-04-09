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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fc6cd8d2d0ab4648ad20392ef0968907917677e9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59209488"
---
# <a name="icorruntimehostswitchinlogicalthreadstate-method"></a><span data-ttu-id="ca9b0-102">ICorRuntimeHost::SwitchInLogicalThreadState-Methode</span><span class="sxs-lookup"><span data-stu-id="ca9b0-102">ICorRuntimeHost::SwitchInLogicalThreadState Method</span></span>
<span data-ttu-id="ca9b0-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="ca9b0-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca9b0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ca9b0-104">Syntax</span></span>  
  
```  
HRESULT SwitchInLogicalThreadState(  
    [in] DWORD *pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca9b0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ca9b0-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="ca9b0-106">[in] Cookie, der die zu verwendende Fiber angibt.</span><span class="sxs-lookup"><span data-stu-id="ca9b0-106">[in] Cookie that indicates the fiber to use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca9b0-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ca9b0-107">Requirements</span></span>  
 <span data-ttu-id="ca9b0-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca9b0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca9b0-109">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ca9b0-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ca9b0-110">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ca9b0-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca9b0-111">**.NET Framework Version:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="ca9b0-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca9b0-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca9b0-112">See also</span></span>

- [<span data-ttu-id="ca9b0-113">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ca9b0-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
