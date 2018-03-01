---
title: ICLRTaskManager::GetCurrentTaskType-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRTaskManager.GetCurrentTaskType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::GetCurrentTaskType
helpviewer_keywords:
- GetCurrentTaskType method [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTaskType method [.NET Framework hosting]
ms.assetid: 6b0d9259-dbe2-45bb-b34d-990f60c73424
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d34ec97c04f4e7871b63d8627903c81e244a30dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtaskmanagergetcurrenttasktype-method"></a><span data-ttu-id="ce524-102">ICLRTaskManager::GetCurrentTaskType-Methode</span><span class="sxs-lookup"><span data-stu-id="ce524-102">ICLRTaskManager::GetCurrentTaskType Method</span></span>
<span data-ttu-id="ce524-103">Ruft den Typ der Aufgabe, die gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ce524-103">Gets the type of the task that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce524-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce524-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentTaskType(  
    [out] ETaskType *pTaskType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ce524-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ce524-105">Parameters</span></span>  
 `pTaskType`  
 <span data-ttu-id="ce524-106">[out] Ein Zeiger auf den Wert der [ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md) -Enumeration, der den Typ der Aufgabe gibt an, die gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ce524-106">[out] A pointer to a value of the [ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md) enumeration that indicates the type of task that is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce524-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ce524-107">Requirements</span></span>  
 <span data-ttu-id="ce524-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce524-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce524-109">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ce524-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ce524-110">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ce524-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ce524-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce524-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce524-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce524-112">See Also</span></span>  
 [<span data-ttu-id="ce524-113">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ce524-113">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
