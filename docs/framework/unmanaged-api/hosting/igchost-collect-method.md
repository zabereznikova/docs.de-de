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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bce005a677dcb74c176a6dddfb2726f6b1fd0e8a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436906"
---
# <a name="igchostcollect-method"></a><span data-ttu-id="11166-102">IGCHost::Collect-Methode</span><span class="sxs-lookup"><span data-stu-id="11166-102">IGCHost::Collect Method</span></span>
<span data-ttu-id="11166-103">Erzwingt, dass eine Sammlung aus, für die angegebene Generation, unabhängig vom Zustand der aktuellen Garbagecollection durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="11166-103">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11166-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="11166-104">Syntax</span></span>  
  
```  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="11166-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="11166-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="11166-106">[in] Die Generierung, für die Garbagecollection durchführen.</span><span class="sxs-lookup"><span data-stu-id="11166-106">[in] The generation on which to perform the garbage collection.</span></span> <span data-ttu-id="11166-107">Der Wert-1 gibt an, dass auf alle Generierungen eine Garbagecollection unterzogen werden.</span><span class="sxs-lookup"><span data-stu-id="11166-107">A value of -1 indicates that all generations will undergo a garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11166-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="11166-108">Requirements</span></span>  
 <span data-ttu-id="11166-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11166-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11166-110">**Header:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="11166-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="11166-111">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="11166-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="11166-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11166-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11166-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11166-113">See Also</span></span>  
 [<span data-ttu-id="11166-114">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="11166-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
