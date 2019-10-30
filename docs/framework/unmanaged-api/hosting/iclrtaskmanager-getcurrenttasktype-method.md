---
title: ICLRTaskManager::GetCurrentTaskType-Methode
ms.date: 03/30/2017
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
ms.openlocfilehash: 848255d44ce8637182f18288d30151a3f0df0912
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092168"
---
# <a name="iclrtaskmanagergetcurrenttasktype-method"></a><span data-ttu-id="0925d-102">ICLRTaskManager::GetCurrentTaskType-Methode</span><span class="sxs-lookup"><span data-stu-id="0925d-102">ICLRTaskManager::GetCurrentTaskType Method</span></span>
<span data-ttu-id="0925d-103">Ruft den Typ der Aufgabe ab, die gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0925d-103">Gets the type of the task that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0925d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0925d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTaskType(  
    [out] ETaskType *pTaskType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0925d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0925d-105">Parameters</span></span>  
 `pTaskType`  
 <span data-ttu-id="0925d-106">vorgenommen Ein Zeiger auf einen Wert der [ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md) -Enumeration, der den Typ des aktuell ausgeführten Tasks angibt.</span><span class="sxs-lookup"><span data-stu-id="0925d-106">[out] A pointer to a value of the [ETaskType](../../../../docs/framework/unmanaged-api/hosting/etasktype-enumeration.md) enumeration that indicates the type of task that is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0925d-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0925d-107">Requirements</span></span>  
 <span data-ttu-id="0925d-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0925d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0925d-109">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="0925d-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0925d-110">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0925d-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0925d-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0925d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0925d-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0925d-112">See also</span></span>

- [<span data-ttu-id="0925d-113">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0925d-113">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
