---
title: IGCHost::GetStats-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost.GetStats
api_location: mscoree.dll
api_type: COM
f1_keywords: GetStats
helpviewer_keywords:
- GetStats method, IGCHost interface [.NET Framework hosting]
- IGCHost::GetStats method [.NET Framework hosting]
ms.assetid: c4ae022c-46ac-4f19-9ddd-09b955f19412
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8d105b0aed9c47d5e2d8ad664744e6424db63961
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="igchostgetstats-method"></a><span data-ttu-id="b6204-102">IGCHost::GetStats-Methode</span><span class="sxs-lookup"><span data-stu-id="b6204-102">IGCHost::GetStats Method</span></span>
<span data-ttu-id="b6204-103">Ruft die Statistiken für den aktuellen Zustand des Garbage Collection-Systems an.</span><span class="sxs-lookup"><span data-stu-id="b6204-103">Gets the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6204-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b6204-104">Syntax</span></span>  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b6204-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b6204-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="b6204-106">[in, out] Ein Zeiger auf eine [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) -Struktur, die die Statistik für den aktuellen Zustand des Garbage Collection-Systems enthält.</span><span class="sxs-lookup"><span data-stu-id="b6204-106">[in, out] A pointer to a [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure that contains the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6204-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b6204-107">Remarks</span></span>  
 <span data-ttu-id="b6204-108">Die Statistiken können von einem intelligenten Verteilung-System verwendet werden, die Garbage Collection-System ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="b6204-108">The statistics can be used by a smart allocation system to help the garbage collection system operate.</span></span> <span data-ttu-id="b6204-109">Beispielsweise kann Zuordnung bestimmt das System nach der Überprüfung der Statistik, die benötigt mehr Arbeitsspeicher hinzufügen oder erzwingen Sie eine Sammlung.</span><span class="sxs-lookup"><span data-stu-id="b6204-109">For example, the allocation system may determine, after reviewing the statistics, that it needs to add more memory or force a collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6204-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b6204-110">Requirements</span></span>  
 <span data-ttu-id="b6204-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6204-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6204-112">**Header:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="b6204-112">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="b6204-113">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b6204-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b6204-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6204-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6204-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b6204-115">See Also</span></span>  
 [<span data-ttu-id="b6204-116">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b6204-116">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
