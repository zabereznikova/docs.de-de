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
ms.openlocfilehash: 5a32fb0480e76f47495590a29c329f54722e2dee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127778"
---
# <a name="icorconfigurationsetgchostcontrol-method"></a><span data-ttu-id="91e4f-102">ICorConfiguration::SetGCHostControl-Methode</span><span class="sxs-lookup"><span data-stu-id="91e4f-102">ICorConfiguration::SetGCHostControl Method</span></span>
<span data-ttu-id="91e4f-103">Legt die Rückruf Schnittstelle fest, die vom Garbage Collector verwendet werden soll, um den Host zum Ändern der Grenzwerte für den virtuellen Arbeitsspeicher anzufordern.</span><span class="sxs-lookup"><span data-stu-id="91e4f-103">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91e4f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="91e4f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCHostControl (  
    [in] IGCHostControl* pGCHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91e4f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="91e4f-105">Parameters</span></span>  
 `pGCHostControl`  
 <span data-ttu-id="91e4f-106">in Ein Zeiger auf ein [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) -Objekt, das dem Garbage Collector ermöglicht, den Host zum Ändern der Grenzwerte für den virtuellen Arbeitsspeicher anzufordern.</span><span class="sxs-lookup"><span data-stu-id="91e4f-106">[in] A pointer to an [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) object that allows the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91e4f-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="91e4f-107">Requirements</span></span>  
 <span data-ttu-id="91e4f-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91e4f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91e4f-109">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="91e4f-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="91e4f-110">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="91e4f-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="91e4f-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91e4f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91e4f-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91e4f-112">See also</span></span>

- [<span data-ttu-id="91e4f-113">ICorConfiguration-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="91e4f-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
