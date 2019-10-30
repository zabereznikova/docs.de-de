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
ms.openlocfilehash: 36eeb7ed4f80979ef2edb930e65963a1db0c894f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134906"
---
# <a name="igchostgetthreadstats-method"></a><span data-ttu-id="e3fa4-102">IGCHost::GetThreadStats-Methode</span><span class="sxs-lookup"><span data-stu-id="e3fa4-102">IGCHost::GetThreadStats Method</span></span>
<span data-ttu-id="e3fa4-103">Ruft die Statistiken pro Thread für Garbage Collection ab.</span><span class="sxs-lookup"><span data-stu-id="e3fa4-103">Gets the per-thread statistics for garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3fa4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e3fa4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadStats (  
    [in] DWORD *pFiberCookie,  
    [in, out] COR_GC_THREAD_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3fa4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e3fa4-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="e3fa4-106">in Ein Zeiger auf ein Fiber Cookie, das den Thread angibt, für den die Statistiken abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e3fa4-106">[in] A pointer to a fiber cookie that specifies the thread for which to retrieve the statistics.</span></span>  
  
 `pStats`  
 <span data-ttu-id="e3fa4-107">[in, out] Ein Zeiger auf eine [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) -Struktur, die die Garbage Collection Statistiken für den angegebenen Thread enthält.</span><span class="sxs-lookup"><span data-stu-id="e3fa4-107">[in, out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) structure that contains the garbage collection statistics for the specified thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3fa4-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e3fa4-108">Requirements</span></span>  
 <span data-ttu-id="e3fa4-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3fa4-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3fa4-110">**Header:** Gchost. idl, gchost. h</span><span class="sxs-lookup"><span data-stu-id="e3fa4-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="e3fa4-111">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e3fa4-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e3fa4-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3fa4-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3fa4-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e3fa4-113">See also</span></span>

- [<span data-ttu-id="e3fa4-114">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e3fa4-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
