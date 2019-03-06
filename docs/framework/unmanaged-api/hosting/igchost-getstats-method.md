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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b8af1de3daf08a8389a5b0e6ebb278646345f9b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57482612"
---
# <a name="igchostgetstats-method"></a><span data-ttu-id="7d03f-102">IGCHost::GetStats-Methode</span><span class="sxs-lookup"><span data-stu-id="7d03f-102">IGCHost::GetStats Method</span></span>
<span data-ttu-id="7d03f-103">Ruft die Statistiken für den aktuellen Zustand des Garbage Collection-Systems ab.</span><span class="sxs-lookup"><span data-stu-id="7d03f-103">Gets the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d03f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7d03f-104">Syntax</span></span>  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d03f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7d03f-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="7d03f-106">[in, out] Ein Zeiger auf eine [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) -Struktur, die die Statistik für den aktuellen Zustand des Garbage Collection-Systems enthält.</span><span class="sxs-lookup"><span data-stu-id="7d03f-106">[in, out] A pointer to a [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure that contains the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d03f-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7d03f-107">Remarks</span></span>  
 <span data-ttu-id="7d03f-108">Die Statistik kann von einem System für die intelligente Zuordnung verwendet werden, die Garbage Collection-System ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="7d03f-108">The statistics can be used by a smart allocation system to help the garbage collection system operate.</span></span> <span data-ttu-id="7d03f-109">Beispielsweise kann das Zuordnungssystem nach der Überprüfung der Statistik, die es benötigt mehr Arbeitsspeicher hinzufügen oder erzwingen Sie eine Sammlung.</span><span class="sxs-lookup"><span data-stu-id="7d03f-109">For example, the allocation system may determine, after reviewing the statistics, that it needs to add more memory or force a collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d03f-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7d03f-110">Requirements</span></span>  
 <span data-ttu-id="7d03f-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d03f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d03f-112">**Header:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="7d03f-112">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="7d03f-113">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7d03f-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7d03f-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d03f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d03f-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d03f-115">See also</span></span>
- [<span data-ttu-id="7d03f-116">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7d03f-116">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
