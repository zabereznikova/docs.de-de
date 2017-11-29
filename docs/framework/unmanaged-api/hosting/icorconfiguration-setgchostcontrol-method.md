---
title: ICorConfiguration::SetGCHostControl-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorConfiguration.SetGCHostControl
api_location: mscoree.dll
api_type: COM
f1_keywords: SetGCHostControl
helpviewer_keywords:
- ICorConfiguration::SetGCHostControl method [.NET Framework hosting]
- SetGCHostControl method [.NET Framework hosting]
ms.assetid: bca6bd79-e288-475a-aa46-6bf81541d966
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 33d01ff208e9814e73c7a658e41819348da6831a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorconfigurationsetgchostcontrol-method"></a><span data-ttu-id="f7706-102">ICorConfiguration::SetGCHostControl-Methode</span><span class="sxs-lookup"><span data-stu-id="f7706-102">ICorConfiguration::SetGCHostControl Method</span></span>
<span data-ttu-id="f7706-103">Legt die Rückrufschnittstelle vom Garbage Collector verwendet werden, um den Host zum Ändern der Grenzen des virtuellen Arbeitsspeichers anzufordern.</span><span class="sxs-lookup"><span data-stu-id="f7706-103">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7706-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f7706-104">Syntax</span></span>  
  
```  
HRESULT SetGCHostControl (  
    [in] IGCHostControl* pGCHostControl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f7706-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f7706-105">Parameters</span></span>  
 `pGCHostControl`  
 <span data-ttu-id="f7706-106">[in] Ein Zeiger auf ein [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) -Objekt, das den Garbage Collector auf den Host zum Ändern der Grenzen des virtuellen Arbeitsspeichers anfordern kann.</span><span class="sxs-lookup"><span data-stu-id="f7706-106">[in] A pointer to an [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) object that allows the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7706-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f7706-107">Requirements</span></span>  
 <span data-ttu-id="f7706-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7706-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7706-109">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f7706-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f7706-110">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f7706-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f7706-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7706-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7706-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7706-112">See Also</span></span>  
 [<span data-ttu-id="f7706-113">ICorConfiguration-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f7706-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
