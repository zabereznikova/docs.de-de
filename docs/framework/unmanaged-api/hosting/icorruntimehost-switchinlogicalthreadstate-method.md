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
ms.openlocfilehash: a4590bcd96226a713ff5535a8bc802c2116f862a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690134"
---
# <a name="icorruntimehostswitchinlogicalthreadstate-method"></a><span data-ttu-id="3a443-102">ICorRuntimeHost::SwitchInLogicalThreadState-Methode</span><span class="sxs-lookup"><span data-stu-id="3a443-102">ICorRuntimeHost::SwitchInLogicalThreadState Method</span></span>

<span data-ttu-id="3a443-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="3a443-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a443-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3a443-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchInLogicalThreadState(  
    [in] DWORD *pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a443-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3a443-105">Parameters</span></span>  

 `pFiberCookie`  
 <span data-ttu-id="3a443-106">in Ein Cookie, das die zu verwendende Fiber angibt.</span><span class="sxs-lookup"><span data-stu-id="3a443-106">[in] Cookie that indicates the fiber to use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a443-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3a443-107">Requirements</span></span>  

 <span data-ttu-id="3a443-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a443-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a443-109">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="3a443-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3a443-110">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3a443-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3a443-111">**.NET Framework Version:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="3a443-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a443-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3a443-112">See also</span></span>

- [<span data-ttu-id="3a443-113">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3a443-113">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
