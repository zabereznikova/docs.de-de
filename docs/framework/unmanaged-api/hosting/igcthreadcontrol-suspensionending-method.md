---
title: IGCThreadControl::SuspensionEnding-Methode
ms.date: 03/30/2017
api_name:
- IGCThreadControl.SuspensionEnding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SuspensionEnding
helpviewer_keywords:
- IGCThreadControl::SuspensionEnding method [.NET Framework hosting]
- SuspensionEnding method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 70814265-c734-4ddc-9502-fe8b28d2b414
topic_type:
- apiref
ms.openlocfilehash: 4638672b1d64a9ea07618212cc514d00996470eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721672"
---
# <a name="igcthreadcontrolsuspensionending-method"></a><span data-ttu-id="d00a4-102">IGCThreadControl::SuspensionEnding-Methode</span><span class="sxs-lookup"><span data-stu-id="d00a4-102">IGCThreadControl::SuspensionEnding Method</span></span>

<span data-ttu-id="d00a4-103">Benachrichtigt den Host, dass die Laufzeit Threads nach einem Garbage Collection oder einer anderen Unterbrechung fortsetzt.</span><span class="sxs-lookup"><span data-stu-id="d00a4-103">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d00a4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d00a4-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionEnding (  
    [in] DWORD Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d00a4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d00a4-105">Parameters</span></span>  

 `Generation`  
 <span data-ttu-id="d00a4-106">in Die Generierung, auf der ein Garbage Collection ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="d00a4-106">[in] The generation on which a garbage collection has been performed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d00a4-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d00a4-107">Remarks</span></span>  

 <span data-ttu-id="d00a4-108">Planen Sie keine Threads während des `SuspensionEnding` Rückrufs neu.</span><span class="sxs-lookup"><span data-stu-id="d00a4-108">Do not reschedule any threads during the `SuspensionEnding` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d00a4-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d00a4-109">Requirements</span></span>  

 <span data-ttu-id="d00a4-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d00a4-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d00a4-111">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="d00a4-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d00a4-112">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d00a4-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d00a4-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d00a4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d00a4-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d00a4-114">See also</span></span>

- [<span data-ttu-id="d00a4-115">IGCThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d00a4-115">IGCThreadControl Interface</span></span>](igcthreadcontrol-interface.md)
