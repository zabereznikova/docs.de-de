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
ms.openlocfilehash: 1e1d63ab28276f69e5b3a762520db8f8300d05bc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134760"
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="227fc-102">IGCThreadControl::SuspensionStarting-Methode</span><span class="sxs-lookup"><span data-stu-id="227fc-102">IGCThreadControl::SuspensionStarting Method</span></span>
<span data-ttu-id="227fc-103">Benachrichtigt den Host, dass die Laufzeit eine Thread Unterbrechung für eine Garbage Collection oder eine andere Unterbrechung beginnt.</span><span class="sxs-lookup"><span data-stu-id="227fc-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="227fc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="227fc-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="227fc-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="227fc-105">Remarks</span></span>  
 <span data-ttu-id="227fc-106">Planen Sie keine Threads während des `SuspensionStarting` Rückrufs neu.</span><span class="sxs-lookup"><span data-stu-id="227fc-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="227fc-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="227fc-107">Requirements</span></span>  
 <span data-ttu-id="227fc-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="227fc-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="227fc-109">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="227fc-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="227fc-110">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="227fc-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="227fc-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="227fc-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="227fc-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="227fc-112">See also</span></span>

- [<span data-ttu-id="227fc-113">IGCThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="227fc-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
