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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700747"
---
# <a name="icorruntimehostlocksheldbylogicalthread-method"></a><span data-ttu-id="b3200-102">ICorRuntimeHost::LocksHeldByLogicalThread-Methode</span><span class="sxs-lookup"><span data-stu-id="b3200-102">ICorRuntimeHost::LocksHeldByLogicalThread Method</span></span>
<span data-ttu-id="b3200-103">Ruft die Anzahl von Sperren, die aktuellen Threads enthält.</span><span class="sxs-lookup"><span data-stu-id="b3200-103">Retrieves the number of locks that current thread holds.</span></span>  
  
 <span data-ttu-id="b3200-104">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="b3200-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3200-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b3200-105">Syntax</span></span>  
  
```  
HRESULT LocksHeldByLogicalThread(  
    [out] DWORD *pCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3200-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b3200-106">Parameters</span></span>  
 `pCount`  
 <span data-ttu-id="b3200-107">[out] Ein Zeiger auf die Anzahl der Sperren, die der aktuelle Thread enthält.</span><span class="sxs-lookup"><span data-stu-id="b3200-107">[out] A pointer to the number of locks that the current thread holds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3200-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b3200-108">Requirements</span></span>  
 <span data-ttu-id="b3200-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3200-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3200-110">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b3200-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b3200-111">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b3200-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b3200-112">**.NET Framework-Versionen:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="b3200-112">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3200-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3200-113">See also</span></span>

- [<span data-ttu-id="b3200-114">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b3200-114">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
