---
title: IGCThreadControl::SuspensionStarting-Methode
ms.date: 03/30/2017
api_name:
- IGCThreadControl.SuspensionStarting
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SuspensionStarting
helpviewer_keywords:
- IGCThreadControl::SuspensionStarting method [.NET Framework hosting]
- SuspensionStarting method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 0af312af-98e9-415e-b182-42e80a1aee51
topic_type:
- apiref
ms.openlocfilehash: 9d39ee79f7734f7dd099a07640ecb06f4f8dcbb3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721659"
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="c6464-102">IGCThreadControl::SuspensionStarting-Methode</span><span class="sxs-lookup"><span data-stu-id="c6464-102">IGCThreadControl::SuspensionStarting Method</span></span>

<span data-ttu-id="c6464-103">Benachrichtigt den Host, dass die Laufzeit eine Thread Unterbrechung für eine Garbage Collection oder eine andere Unterbrechung beginnt.</span><span class="sxs-lookup"><span data-stu-id="c6464-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6464-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c6464-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="c6464-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c6464-105">Remarks</span></span>  

 <span data-ttu-id="c6464-106">Planen Sie keine Threads während des `SuspensionStarting` Rückrufs neu.</span><span class="sxs-lookup"><span data-stu-id="c6464-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6464-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c6464-107">Requirements</span></span>  

 <span data-ttu-id="c6464-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6464-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6464-109">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="c6464-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c6464-110">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c6464-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c6464-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6464-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6464-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c6464-112">See also</span></span>

- [<span data-ttu-id="c6464-113">IGCThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c6464-113">IGCThreadControl Interface</span></span>](igcthreadcontrol-interface.md)
