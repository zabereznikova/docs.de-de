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
ms.openlocfilehash: e41ead54b50b8b28ebd9ee9c97d15ca6c71e7313
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690121"
---
# <a name="icorruntimehostswitchoutlogicalthreadstate-method"></a><span data-ttu-id="8a90c-102">ICorRuntimeHost::SwitchOutLogicalThreadState-Methode</span><span class="sxs-lookup"><span data-stu-id="8a90c-102">ICorRuntimeHost::SwitchOutLogicalThreadState Method</span></span>

<span data-ttu-id="8a90c-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="8a90c-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a90c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8a90c-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchOutLogicalThreadState(  
    [out] DWORD **pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a90c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8a90c-105">Parameters</span></span>  

 `pFiberCookie`  
 <span data-ttu-id="8a90c-106">vorgenommen Ein Cookie, das angibt, dass die Fiber ausgeschaltet wird.</span><span class="sxs-lookup"><span data-stu-id="8a90c-106">[out] Cookie that indicates the fiber being switched out.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a90c-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8a90c-107">Requirements</span></span>  

 <span data-ttu-id="8a90c-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a90c-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a90c-109">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="8a90c-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8a90c-110">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8a90c-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8a90c-111">**.NET Framework Version:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="8a90c-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a90c-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8a90c-112">See also</span></span>

- [<span data-ttu-id="8a90c-113">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8a90c-113">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
