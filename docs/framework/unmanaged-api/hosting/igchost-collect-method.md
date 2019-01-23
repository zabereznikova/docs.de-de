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
ms.openlocfilehash: f911d99470b9870f5c42d4170a4024123c10e7f3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54511120"
---
# <a name="igchostcollect-method"></a><span data-ttu-id="878d6-102">IGCHost::Collect-Methode</span><span class="sxs-lookup"><span data-stu-id="878d6-102">IGCHost::Collect Method</span></span>
<span data-ttu-id="878d6-103">Erzwingt, dass eine Collection für die angegebene Generation, unabhängig vom Status des aktuellen Garbagecollection durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="878d6-103">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="878d6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="878d6-104">Syntax</span></span>  
  
```  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="878d6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="878d6-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="878d6-106">[in] Die Objektgeneration, für den die Garbagecollection ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="878d6-106">[in] The generation on which to perform the garbage collection.</span></span> <span data-ttu-id="878d6-107">Der Wert-1 gibt an, dass alle Generationen eine Garbagecollection unterzogen werden.</span><span class="sxs-lookup"><span data-stu-id="878d6-107">A value of -1 indicates that all generations will undergo a garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="878d6-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="878d6-108">Requirements</span></span>  
 <span data-ttu-id="878d6-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="878d6-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="878d6-110">**Header:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="878d6-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="878d6-111">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="878d6-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="878d6-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="878d6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="878d6-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="878d6-113">See also</span></span>
- [<span data-ttu-id="878d6-114">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="878d6-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
