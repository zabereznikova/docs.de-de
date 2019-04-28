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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1291d4e69843db7bd90af07291da415220d98807
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700292"
---
# <a name="icorruntimehostswitchoutlogicalthreadstate-method"></a><span data-ttu-id="a66a4-102">ICorRuntimeHost::SwitchOutLogicalThreadState-Methode</span><span class="sxs-lookup"><span data-stu-id="a66a4-102">ICorRuntimeHost::SwitchOutLogicalThreadState Method</span></span>
<span data-ttu-id="a66a4-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="a66a4-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a66a4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a66a4-104">Syntax</span></span>  
  
```  
HRESULT SwitchOutLogicalThreadState(  
    [out] DWORD **pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a66a4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a66a4-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="a66a4-106">[out] Cookie, der die Verbindungslinie, die ausgelagert wird angibt.</span><span class="sxs-lookup"><span data-stu-id="a66a4-106">[out] Cookie that indicates the fiber being switched out.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a66a4-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a66a4-107">Requirements</span></span>  
 <span data-ttu-id="a66a4-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a66a4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a66a4-109">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a66a4-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a66a4-110">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a66a4-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a66a4-111">**.NET Framework Version:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="a66a4-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a66a4-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a66a4-112">See also</span></span>

- [<span data-ttu-id="a66a4-113">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a66a4-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
