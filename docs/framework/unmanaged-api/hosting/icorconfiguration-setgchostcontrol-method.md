---
title: ICorConfiguration::SetGCHostControl-Methode
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCHostControl
helpviewer_keywords:
- ICorConfiguration::SetGCHostControl method [.NET Framework hosting]
- SetGCHostControl method [.NET Framework hosting]
ms.assetid: bca6bd79-e288-475a-aa46-6bf81541d966
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 50a92058e8a394b95c690d19f1bafdddbed8246a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135992"
---
# <a name="icorconfigurationsetgchostcontrol-method"></a><span data-ttu-id="4f268-102">ICorConfiguration::SetGCHostControl-Methode</span><span class="sxs-lookup"><span data-stu-id="4f268-102">ICorConfiguration::SetGCHostControl Method</span></span>
<span data-ttu-id="4f268-103">Legt die Rückrufschnittstelle, die vom Garbage Collector verwendet werden, um den Host zum Ändern der Grenzen des virtuellen Arbeitsspeichers anzufordern.</span><span class="sxs-lookup"><span data-stu-id="4f268-103">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f268-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4f268-104">Syntax</span></span>  
  
```  
HRESULT SetGCHostControl (  
    [in] IGCHostControl* pGCHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f268-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4f268-105">Parameters</span></span>  
 `pGCHostControl`  
 <span data-ttu-id="4f268-106">[in] Ein Zeiger auf ein [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) Objekt, das von der Garbage Collector, den Host zum Ändern der Grenzen des virtuellen Speichers ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="4f268-106">[in] A pointer to an [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) object that allows the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f268-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4f268-107">Requirements</span></span>  
 <span data-ttu-id="4f268-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f268-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f268-109">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4f268-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4f268-110">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4f268-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="4f268-111">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="4f268-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4f268-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f268-112">See also</span></span>

- [<span data-ttu-id="4f268-113">ICorConfiguration-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4f268-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
