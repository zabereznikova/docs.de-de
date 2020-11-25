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
ms.openlocfilehash: 718e6f3f19a5c368091c8a8aad3bd1f6598228df
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727276"
---
# <a name="ihosttaskmanagergetstackguarantee-method"></a><span data-ttu-id="1d817-102">IHostTaskManager::GetStackGuarantee-Methode</span><span class="sxs-lookup"><span data-stu-id="1d817-102">IHostTaskManager::GetStackGuarantee Method</span></span>

<span data-ttu-id="1d817-103">Ruft die Menge des Stapel Platzes ab, der nach Abschluss eines Stapel Vorgangs garantiert verfügbar ist, jedoch vor dem Schließen eines Prozesses.</span><span class="sxs-lookup"><span data-stu-id="1d817-103">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d817-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1d817-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackGuarantee(  
    [out] ULONG *pGuarantee  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d817-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1d817-105">Parameters</span></span>  

 `pGuarantee`  
 <span data-ttu-id="1d817-106">vorgenommen Ein Zeiger auf die Anzahl der verfügbaren Bytes.</span><span class="sxs-lookup"><span data-stu-id="1d817-106">[out] A pointer to the number of bytes that are available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d817-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1d817-107">Requirements</span></span>  

 <span data-ttu-id="1d817-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d817-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d817-109">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="1d817-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1d817-110">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1d817-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1d817-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d817-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d817-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1d817-112">See also</span></span>

- [<span data-ttu-id="1d817-113">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1d817-113">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
