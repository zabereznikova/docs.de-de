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
ms.openlocfilehash: 2acabe66e3b6b5652df20e31a9d2294c2396b54b
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805103"
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="e5884-102">IGCThreadControl::SuspensionStarting-Methode</span><span class="sxs-lookup"><span data-stu-id="e5884-102">IGCThreadControl::SuspensionStarting Method</span></span>
<span data-ttu-id="e5884-103">Benachrichtigt den Host, dass die Laufzeit eine Thread Unterbrechung für eine Garbage Collection oder eine andere Unterbrechung beginnt.</span><span class="sxs-lookup"><span data-stu-id="e5884-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5884-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e5884-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="e5884-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e5884-105">Remarks</span></span>  
 <span data-ttu-id="e5884-106">Planen Sie keine Threads während des `SuspensionStarting` Rückrufs neu.</span><span class="sxs-lookup"><span data-stu-id="e5884-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5884-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e5884-107">Requirements</span></span>  
 <span data-ttu-id="e5884-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5884-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5884-109">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="e5884-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e5884-110">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e5884-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e5884-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5884-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5884-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e5884-112">See also</span></span>

- [<span data-ttu-id="e5884-113">IGCThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e5884-113">IGCThreadControl Interface</span></span>](igcthreadcontrol-interface.md)
