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
ms.openlocfilehash: d76242eb8539f2e8dffbf39b7eaf595664bdce8e
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842022"
---
# <a name="ihosttaskmanagergetstackguarantee-method"></a><span data-ttu-id="af036-102">IHostTaskManager::GetStackGuarantee-Methode</span><span class="sxs-lookup"><span data-stu-id="af036-102">IHostTaskManager::GetStackGuarantee Method</span></span>
<span data-ttu-id="af036-103">Ruft die Menge des Stapel Platzes ab, der nach Abschluss eines Stapel Vorgangs garantiert verfügbar ist, jedoch vor dem Schließen eines Prozesses.</span><span class="sxs-lookup"><span data-stu-id="af036-103">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af036-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="af036-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackGuarantee(  
    [out] ULONG *pGuarantee  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af036-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="af036-105">Parameters</span></span>  
 `pGuarantee`  
 <span data-ttu-id="af036-106">vorgenommen Ein Zeiger auf die Anzahl der verfügbaren Bytes.</span><span class="sxs-lookup"><span data-stu-id="af036-106">[out] A pointer to the number of bytes that are available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af036-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="af036-107">Requirements</span></span>  
 <span data-ttu-id="af036-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af036-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af036-109">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="af036-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="af036-110">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="af036-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="af036-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af036-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af036-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af036-112">See also</span></span>

- [<span data-ttu-id="af036-113">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="af036-113">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
