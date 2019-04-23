---
title: IHostTaskManager::GetStackGuarantee-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.GetStackGuarantee
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::GetStackGuarantee
helpviewer_keywords:
- GetStackGuarantee method [.NET Framework hosting]
- IHostTaskManager::GetStackGuarantee method [.NET Framework hosting]
ms.assetid: 8176d732-c25c-4520-811d-e3310f339947
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea1c1f998febccbc80fb10cef5a8dfd229e1987e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59095944"
---
# <a name="ihosttaskmanagergetstackguarantee-method"></a><span data-ttu-id="d5ea7-102">IHostTaskManager::GetStackGuarantee-Methode</span><span class="sxs-lookup"><span data-stu-id="d5ea7-102">IHostTaskManager::GetStackGuarantee Method</span></span>
<span data-ttu-id="d5ea7-103">Ruft die Menge an Stapelspeicher, der garantiert verfügbar, sobald ein Stack-Vorgang abgeschlossen wird, aber vor dem Endtag eines Prozesses ab.</span><span class="sxs-lookup"><span data-stu-id="d5ea7-103">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5ea7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d5ea7-104">Syntax</span></span>  
  
```  
HRESULT GetStackGuarantee(  
    [out] ULONG *pGuarantee  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5ea7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d5ea7-105">Parameters</span></span>  
 `pGuarantee`  
 <span data-ttu-id="d5ea7-106">[out] Ein Zeiger auf die Anzahl der Bytes, die verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="d5ea7-106">[out] A pointer to the number of bytes that are available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5ea7-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d5ea7-107">Requirements</span></span>  
 <span data-ttu-id="d5ea7-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5ea7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5ea7-109">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d5ea7-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d5ea7-110">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d5ea7-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d5ea7-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5ea7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5ea7-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5ea7-112">See also</span></span>

- [<span data-ttu-id="d5ea7-113">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5ea7-113">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
