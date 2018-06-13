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
ms.openlocfilehash: c3e0d6f68ffa5280d4616d4fa4ac60b4cb86f6a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437764"
---
# <a name="igchostgetstats-method"></a><span data-ttu-id="4268f-102">IGCHost::GetStats-Methode</span><span class="sxs-lookup"><span data-stu-id="4268f-102">IGCHost::GetStats Method</span></span>
<span data-ttu-id="4268f-103">Ruft die Statistiken für den aktuellen Zustand des Garbage Collection-Systems an.</span><span class="sxs-lookup"><span data-stu-id="4268f-103">Gets the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4268f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4268f-104">Syntax</span></span>  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4268f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4268f-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="4268f-106">[in, out] Ein Zeiger auf eine [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) -Struktur, die die Statistik für den aktuellen Zustand des Garbage Collection-Systems enthält.</span><span class="sxs-lookup"><span data-stu-id="4268f-106">[in, out] A pointer to a [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure that contains the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4268f-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4268f-107">Remarks</span></span>  
 <span data-ttu-id="4268f-108">Die Statistiken können von einem intelligenten Verteilung-System verwendet werden, die Garbage Collection-System ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="4268f-108">The statistics can be used by a smart allocation system to help the garbage collection system operate.</span></span> <span data-ttu-id="4268f-109">Beispielsweise kann Zuordnung bestimmt das System nach der Überprüfung der Statistik, die benötigt mehr Arbeitsspeicher hinzufügen oder erzwingen Sie eine Sammlung.</span><span class="sxs-lookup"><span data-stu-id="4268f-109">For example, the allocation system may determine, after reviewing the statistics, that it needs to add more memory or force a collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4268f-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4268f-110">Requirements</span></span>  
 <span data-ttu-id="4268f-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4268f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4268f-112">**Header:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="4268f-112">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="4268f-113">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4268f-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4268f-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4268f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4268f-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4268f-115">See Also</span></span>  
 [<span data-ttu-id="4268f-116">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4268f-116">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
