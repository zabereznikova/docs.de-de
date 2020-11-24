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
ms.openlocfilehash: c48b580e632d67db5a9826c210415adab1bdba96
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95670068"
---
# <a name="igchostgetthreadstats-method"></a><span data-ttu-id="32489-102">IGCHost::GetThreadStats-Methode</span><span class="sxs-lookup"><span data-stu-id="32489-102">IGCHost::GetThreadStats Method</span></span>

<span data-ttu-id="32489-103">Ruft die Statistiken pro Thread für Garbage Collection ab.</span><span class="sxs-lookup"><span data-stu-id="32489-103">Gets the per-thread statistics for garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32489-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="32489-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadStats (  
    [in] DWORD *pFiberCookie,  
    [in, out] COR_GC_THREAD_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32489-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="32489-105">Parameters</span></span>  

 `pFiberCookie`  
 <span data-ttu-id="32489-106">in Ein Zeiger auf ein Fiber Cookie, das den Thread angibt, für den die Statistiken abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="32489-106">[in] A pointer to a fiber cookie that specifies the thread for which to retrieve the statistics.</span></span>  
  
 `pStats`  
 <span data-ttu-id="32489-107">[in, out] Ein Zeiger auf eine [COR_GC_THREAD_STATS](cor-gc-thread-stats-structure.md) -Struktur, die die Garbage Collection Statistiken für den angegebenen Thread enthält.</span><span class="sxs-lookup"><span data-stu-id="32489-107">[in, out] A pointer to a [COR_GC_THREAD_STATS](cor-gc-thread-stats-structure.md) structure that contains the garbage collection statistics for the specified thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32489-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="32489-108">Requirements</span></span>  

 <span data-ttu-id="32489-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32489-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32489-110">**Header:** Gchost. idl, gchost. h</span><span class="sxs-lookup"><span data-stu-id="32489-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="32489-111">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="32489-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="32489-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32489-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32489-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="32489-113">See also</span></span>

- [<span data-ttu-id="32489-114">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="32489-114">IGCHost Interface</span></span>](igchost-interface.md)
