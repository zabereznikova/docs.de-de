---
title: IGCHost::GetThreadStats-Methode
ms.date: 03/30/2017
api_name:
- IGCHost.GetThreadStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetThreadStats
helpviewer_keywords:
- IGCHost::GetThreadStats method [.NET Framework hosting]
- GetThreadStats method [.NET Framework hosting]
ms.assetid: 826baa9b-9218-4736-a509-7ab193b125a0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 87e318c4f2367e8c66910978f4a9c89f36c95632
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766506"
---
# <a name="igchostgetthreadstats-method"></a><span data-ttu-id="e5c5d-102">IGCHost::GetThreadStats-Methode</span><span class="sxs-lookup"><span data-stu-id="e5c5d-102">IGCHost::GetThreadStats Method</span></span>
<span data-ttu-id="e5c5d-103">Ruft die Statistiken pro Thread für die Garbagecollection ab.</span><span class="sxs-lookup"><span data-stu-id="e5c5d-103">Gets the per-thread statistics for garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5c5d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e5c5d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadStats (  
    [in] DWORD *pFiberCookie,  
    [in, out] COR_GC_THREAD_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5c5d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e5c5d-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="e5c5d-106">[in] Ein Zeiger auf ein Fibercookie, der angibt, den Thread für die die Statistiken abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e5c5d-106">[in] A pointer to a fiber cookie that specifies the thread for which to retrieve the statistics.</span></span>  
  
 `pStats`  
 <span data-ttu-id="e5c5d-107">[in, out] Ein Zeiger auf eine [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) Struktur, die die Garbage Collection-Statistik für den angegebenen Thread enthält.</span><span class="sxs-lookup"><span data-stu-id="e5c5d-107">[in, out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) structure that contains the garbage collection statistics for the specified thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5c5d-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e5c5d-108">Requirements</span></span>  
 <span data-ttu-id="e5c5d-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5c5d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5c5d-110">**Header:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="e5c5d-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="e5c5d-111">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e5c5d-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e5c5d-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5c5d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5c5d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5c5d-113">See also</span></span>

- [<span data-ttu-id="e5c5d-114">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e5c5d-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
