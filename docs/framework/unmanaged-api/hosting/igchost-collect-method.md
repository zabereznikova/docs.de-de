---
title: IGCHost::Collect-Methode
ms.date: 03/30/2017
api_name:
- IGCHost.Collect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Collect
helpviewer_keywords:
- Collect method, IGCHost interface [.NET Framework hosting]
- IGCHost::Collect method [.NET Framework hosting]
ms.assetid: fc7d9448-3186-494d-9f0d-ea39717e9a82
topic_type:
- apiref
ms.openlocfilehash: f32b91f0d47449f80c38542162035999d616813b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95670139"
---
# <a name="igchostcollect-method"></a><span data-ttu-id="b2e90-102">IGCHost::Collect-Methode</span><span class="sxs-lookup"><span data-stu-id="b2e90-102">IGCHost::Collect Method</span></span>

<span data-ttu-id="b2e90-103">Erzwingt, dass eine Auflistung für die angegebene Generierung stattfindet, unabhängig vom Zustand des aktuellen Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b2e90-103">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2e90-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b2e90-104">Syntax</span></span>  
  
```cpp  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2e90-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b2e90-105">Parameters</span></span>  

 `Generation`  
 <span data-ttu-id="b2e90-106">in Die Generierung, auf der die Garbage Collection durchgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b2e90-106">[in] The generation on which to perform the garbage collection.</span></span> <span data-ttu-id="b2e90-107">Der Wert-1 gibt an, dass alle Generationen einem Garbage Collection unterzogen werden.</span><span class="sxs-lookup"><span data-stu-id="b2e90-107">A value of -1 indicates that all generations will undergo a garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2e90-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b2e90-108">Requirements</span></span>  

 <span data-ttu-id="b2e90-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2e90-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2e90-110">**Header:** Gchost. idl, gchost. h</span><span class="sxs-lookup"><span data-stu-id="b2e90-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="b2e90-111">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b2e90-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b2e90-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2e90-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2e90-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b2e90-113">See also</span></span>

- [<span data-ttu-id="b2e90-114">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b2e90-114">IGCHost Interface</span></span>](igchost-interface.md)
