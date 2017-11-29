---
title: IGCHost::Collect-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost.Collect
api_location: mscoree.dll
api_type: COM
f1_keywords: Collect
helpviewer_keywords:
- Collect method, IGCHost interface [.NET Framework hosting]
- IGCHost::Collect method [.NET Framework hosting]
ms.assetid: fc7d9448-3186-494d-9f0d-ea39717e9a82
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d97a988db48cc9bfdf8cf1e260c28e0169eb73f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="igchostcollect-method"></a><span data-ttu-id="aadfa-102">IGCHost::Collect-Methode</span><span class="sxs-lookup"><span data-stu-id="aadfa-102">IGCHost::Collect Method</span></span>
<span data-ttu-id="aadfa-103">Erzwingt, dass eine Sammlung aus, für die angegebene Generation, unabhängig vom Zustand der aktuellen Garbagecollection durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="aadfa-103">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aadfa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="aadfa-104">Syntax</span></span>  
  
```  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aadfa-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="aadfa-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="aadfa-106">[in] Die Generierung, für die Garbagecollection durchführen.</span><span class="sxs-lookup"><span data-stu-id="aadfa-106">[in] The generation on which to perform the garbage collection.</span></span> <span data-ttu-id="aadfa-107">Der Wert-1 gibt an, dass auf alle Generierungen eine Garbagecollection unterzogen werden.</span><span class="sxs-lookup"><span data-stu-id="aadfa-107">A value of -1 indicates that all generations will undergo a garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aadfa-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="aadfa-108">Requirements</span></span>  
 <span data-ttu-id="aadfa-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aadfa-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aadfa-110">**Header:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="aadfa-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="aadfa-111">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="aadfa-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aadfa-112">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aadfa-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aadfa-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aadfa-113">See Also</span></span>  
 [<span data-ttu-id="aadfa-114">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="aadfa-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
