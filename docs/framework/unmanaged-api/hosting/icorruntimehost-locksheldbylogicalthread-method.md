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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 90af015de4428f75330de89978a7fc0a4b26750b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144195"
---
# <a name="icorruntimehostlocksheldbylogicalthread-method"></a><span data-ttu-id="2e658-102">ICorRuntimeHost::LocksHeldByLogicalThread-Methode</span><span class="sxs-lookup"><span data-stu-id="2e658-102">ICorRuntimeHost::LocksHeldByLogicalThread Method</span></span>
<span data-ttu-id="2e658-103">Ruft die Anzahl von Sperren, die aktuellen Threads enthält.</span><span class="sxs-lookup"><span data-stu-id="2e658-103">Retrieves the number of locks that current thread holds.</span></span>  
  
 <span data-ttu-id="2e658-104">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="2e658-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e658-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2e658-105">Syntax</span></span>  
  
```  
HRESULT LocksHeldByLogicalThread(  
    [out] DWORD *pCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e658-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="2e658-106">Parameters</span></span>  
 `pCount`  
 <span data-ttu-id="2e658-107">[out] Ein Zeiger auf die Anzahl der Sperren, die der aktuelle Thread enthält.</span><span class="sxs-lookup"><span data-stu-id="2e658-107">[out] A pointer to the number of locks that the current thread holds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e658-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2e658-108">Requirements</span></span>  
 <span data-ttu-id="2e658-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e658-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e658-110">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2e658-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2e658-111">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2e658-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2e658-112">**.NET Framework-Versionen:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="2e658-112">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e658-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e658-113">See also</span></span>

- [<span data-ttu-id="2e658-114">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2e658-114">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
