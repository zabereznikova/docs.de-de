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
ms.openlocfilehash: 7e664d88bf9f67e936e693b663f27ca490da13ed
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95670107"
---
# <a name="igchostgetstats-method"></a><span data-ttu-id="051b0-102">IGCHost::GetStats-Methode</span><span class="sxs-lookup"><span data-stu-id="051b0-102">IGCHost::GetStats Method</span></span>

<span data-ttu-id="051b0-103">Ruft die Statistiken für den aktuellen Status des Garbage Collection Systems ab.</span><span class="sxs-lookup"><span data-stu-id="051b0-103">Gets the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="051b0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="051b0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="051b0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="051b0-105">Parameters</span></span>  

 `pStats`  
 <span data-ttu-id="051b0-106">[in, out] Ein Zeiger auf eine [COR_GC_STATS](cor-gc-stats-structure.md) -Struktur, die die Statistiken für den aktuellen Status des Garbage Collection Systems enthält.</span><span class="sxs-lookup"><span data-stu-id="051b0-106">[in, out] A pointer to a [COR_GC_STATS](cor-gc-stats-structure.md) structure that contains the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="051b0-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="051b0-107">Remarks</span></span>  

 <span data-ttu-id="051b0-108">Die Statistiken können von einem intelligenten Zuordnungs System verwendet werden, um das Garbage Collection System zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="051b0-108">The statistics can be used by a smart allocation system to help the garbage collection system operate.</span></span> <span data-ttu-id="051b0-109">Beispielsweise kann das Zuordnungs System nach dem Überprüfen der Statistik feststellen, dass es mehr Arbeitsspeicher hinzufügen oder eine Sammlung erzwingen muss.</span><span class="sxs-lookup"><span data-stu-id="051b0-109">For example, the allocation system may determine, after reviewing the statistics, that it needs to add more memory or force a collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="051b0-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="051b0-110">Requirements</span></span>  

 <span data-ttu-id="051b0-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="051b0-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="051b0-112">**Header:** Gchost. idl, gchost. h</span><span class="sxs-lookup"><span data-stu-id="051b0-112">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="051b0-113">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="051b0-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="051b0-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="051b0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="051b0-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="051b0-115">See also</span></span>

- [<span data-ttu-id="051b0-116">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="051b0-116">IGCHost Interface</span></span>](igchost-interface.md)
