---
title: IGCHost::GetStats-Methode
ms.date: 03/30/2017
api_name:
- IGCHost.GetStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetStats
helpviewer_keywords:
- GetStats method, IGCHost interface [.NET Framework hosting]
- IGCHost::GetStats method [.NET Framework hosting]
ms.assetid: c4ae022c-46ac-4f19-9ddd-09b955f19412
topic_type:
- apiref
ms.openlocfilehash: c86786a34ff236fb57a1ea6bc4d00b9cd5c4a717
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134897"
---
# <a name="igchostgetstats-method"></a><span data-ttu-id="9d904-102">IGCHost::GetStats-Methode</span><span class="sxs-lookup"><span data-stu-id="9d904-102">IGCHost::GetStats Method</span></span>
<span data-ttu-id="9d904-103">Ruft die Statistiken für den aktuellen Status des Garbage Collection Systems ab.</span><span class="sxs-lookup"><span data-stu-id="9d904-103">Gets the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d904-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9d904-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d904-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9d904-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="9d904-106">[in, out] Ein Zeiger auf eine [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) -Struktur, die die Statistiken für den aktuellen Status des Garbage Collection Systems enthält.</span><span class="sxs-lookup"><span data-stu-id="9d904-106">[in, out] A pointer to a [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure that contains the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d904-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9d904-107">Remarks</span></span>  
 <span data-ttu-id="9d904-108">Die Statistiken können von einem intelligenten Zuordnungs System verwendet werden, um das Garbage Collection System zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="9d904-108">The statistics can be used by a smart allocation system to help the garbage collection system operate.</span></span> <span data-ttu-id="9d904-109">Beispielsweise kann das Zuordnungs System nach dem Überprüfen der Statistik feststellen, dass es mehr Arbeitsspeicher hinzufügen oder eine Sammlung erzwingen muss.</span><span class="sxs-lookup"><span data-stu-id="9d904-109">For example, the allocation system may determine, after reviewing the statistics, that it needs to add more memory or force a collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d904-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9d904-110">Requirements</span></span>  
 <span data-ttu-id="9d904-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d904-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d904-112">**Header:** Gchost. idl, gchost. h</span><span class="sxs-lookup"><span data-stu-id="9d904-112">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="9d904-113">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9d904-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9d904-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d904-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d904-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d904-115">See also</span></span>

- [<span data-ttu-id="9d904-116">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9d904-116">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
