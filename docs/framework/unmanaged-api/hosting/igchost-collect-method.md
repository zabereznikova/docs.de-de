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
ms.openlocfilehash: e20ea6addc1ae3f99b4b3d65f532e0128ac160b3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134972"
---
# <a name="igchostcollect-method"></a><span data-ttu-id="e6141-102">IGCHost::Collect-Methode</span><span class="sxs-lookup"><span data-stu-id="e6141-102">IGCHost::Collect Method</span></span>
<span data-ttu-id="e6141-103">Erzwingt, dass eine Auflistung für die angegebene Generierung stattfindet, unabhängig vom Zustand des aktuellen Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="e6141-103">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6141-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e6141-104">Syntax</span></span>  
  
```cpp  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6141-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e6141-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="e6141-106">in Die Generierung, auf der die Garbage Collection durchgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e6141-106">[in] The generation on which to perform the garbage collection.</span></span> <span data-ttu-id="e6141-107">Der Wert-1 gibt an, dass alle Generationen einem Garbage Collection unterzogen werden.</span><span class="sxs-lookup"><span data-stu-id="e6141-107">A value of -1 indicates that all generations will undergo a garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6141-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e6141-108">Requirements</span></span>  
 <span data-ttu-id="e6141-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6141-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6141-110">**Header:** Gchost. idl, gchost. h</span><span class="sxs-lookup"><span data-stu-id="e6141-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="e6141-111">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e6141-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6141-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6141-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6141-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6141-113">See also</span></span>

- [<span data-ttu-id="e6141-114">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e6141-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
