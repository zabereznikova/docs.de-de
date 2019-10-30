---
title: ICorRuntimeHost::LocksHeldByLogicalThread-Methode
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.LocksHeldByLogicalThread
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::LocksHeldByLogicalThread
helpviewer_keywords:
- ICorRuntimeHost::LocksHeldByLogicalThread method [.NET Framework hosting]
- LocksHeldByLogicalThread method [.NET Framework hosting]
ms.assetid: c3601255-d894-4d7c-b1df-c31334551700
topic_type:
- apiref
ms.openlocfilehash: f6ef7e06d94cb22d266949927cb15105b1602d3a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139528"
---
# <a name="icorruntimehostlocksheldbylogicalthread-method"></a><span data-ttu-id="2390b-102">ICorRuntimeHost::LocksHeldByLogicalThread-Methode</span><span class="sxs-lookup"><span data-stu-id="2390b-102">ICorRuntimeHost::LocksHeldByLogicalThread Method</span></span>
<span data-ttu-id="2390b-103">Ruft die Anzahl der Sperren ab, die der aktuelle Thread enthält.</span><span class="sxs-lookup"><span data-stu-id="2390b-103">Retrieves the number of locks that current thread holds.</span></span>  
  
 <span data-ttu-id="2390b-104">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="2390b-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2390b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2390b-105">Syntax</span></span>  
  
```cpp  
HRESULT LocksHeldByLogicalThread(  
    [out] DWORD *pCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2390b-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="2390b-106">Parameters</span></span>  
 `pCount`  
 <span data-ttu-id="2390b-107">vorgenommen Ein Zeiger auf die Anzahl der Sperren, die der aktuelle Thread enthält.</span><span class="sxs-lookup"><span data-stu-id="2390b-107">[out] A pointer to the number of locks that the current thread holds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2390b-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2390b-108">Requirements</span></span>  
 <span data-ttu-id="2390b-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2390b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2390b-110">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="2390b-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2390b-111">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2390b-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2390b-112">**.NET Framework Versionen:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="2390b-112">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2390b-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2390b-113">See also</span></span>

- [<span data-ttu-id="2390b-114">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2390b-114">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
