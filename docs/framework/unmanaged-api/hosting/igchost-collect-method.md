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
ms.openlocfilehash: 9c4fa79f4918412720592bce449a001a349ae657
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766565"
---
# <a name="igchostcollect-method"></a><span data-ttu-id="f297a-102">IGCHost::Collect-Methode</span><span class="sxs-lookup"><span data-stu-id="f297a-102">IGCHost::Collect Method</span></span>
<span data-ttu-id="f297a-103">Erzwingt, dass eine Collection für die angegebene Generation, unabhängig vom Status des aktuellen Garbagecollection durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="f297a-103">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f297a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f297a-104">Syntax</span></span>  
  
```cpp  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f297a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f297a-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="f297a-106">[in] Die Objektgeneration, für den die Garbagecollection ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f297a-106">[in] The generation on which to perform the garbage collection.</span></span> <span data-ttu-id="f297a-107">Der Wert-1 gibt an, dass alle Generationen eine Garbagecollection unterzogen werden.</span><span class="sxs-lookup"><span data-stu-id="f297a-107">A value of -1 indicates that all generations will undergo a garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f297a-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f297a-108">Requirements</span></span>  
 <span data-ttu-id="f297a-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f297a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f297a-110">**Header:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="f297a-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="f297a-111">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f297a-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f297a-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f297a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f297a-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f297a-113">See also</span></span>

- [<span data-ttu-id="f297a-114">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f297a-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
