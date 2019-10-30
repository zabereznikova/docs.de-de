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
ms.openlocfilehash: 22ec34c82d0f8e550dfc8941f2c048ebed6cf1d7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133035"
---
# <a name="ihosttaskmanagergetstackguarantee-method"></a><span data-ttu-id="b4d4a-102">IHostTaskManager::GetStackGuarantee-Methode</span><span class="sxs-lookup"><span data-stu-id="b4d4a-102">IHostTaskManager::GetStackGuarantee Method</span></span>
<span data-ttu-id="b4d4a-103">Ruft die Menge des Stapel Platzes ab, der nach Abschluss eines Stapel Vorgangs garantiert verfügbar ist, jedoch vor dem Schließen eines Prozesses.</span><span class="sxs-lookup"><span data-stu-id="b4d4a-103">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4d4a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4d4a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackGuarantee(  
    [out] ULONG *pGuarantee  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4d4a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b4d4a-105">Parameters</span></span>  
 `pGuarantee`  
 <span data-ttu-id="b4d4a-106">vorgenommen Ein Zeiger auf die Anzahl der verfügbaren Bytes.</span><span class="sxs-lookup"><span data-stu-id="b4d4a-106">[out] A pointer to the number of bytes that are available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4d4a-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b4d4a-107">Requirements</span></span>  
 <span data-ttu-id="b4d4a-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4d4a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4d4a-109">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="b4d4a-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b4d4a-110">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b4d4a-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b4d4a-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4d4a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4d4a-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4d4a-112">See also</span></span>

- [<span data-ttu-id="b4d4a-113">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b4d4a-113">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
