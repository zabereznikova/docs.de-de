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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ff0c95ea79978c0b58057ec06fea231f5632c941
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54702651"
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="421d5-102">IGCThreadControl::SuspensionStarting-Methode</span><span class="sxs-lookup"><span data-stu-id="421d5-102">IGCThreadControl::SuspensionStarting Method</span></span>
<span data-ttu-id="421d5-103">Benachrichtigt den Host, dass die Laufzeit eine Threadunterbrechung für eine Garbagecollection oder einer anderen Unterbrechung beginnt.</span><span class="sxs-lookup"><span data-stu-id="421d5-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="421d5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="421d5-104">Syntax</span></span>  
  
```  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="421d5-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="421d5-105">Remarks</span></span>  
 <span data-ttu-id="421d5-106">Darf nicht verlegt werden alle Threads, während die `SuspensionStarting` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="421d5-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="421d5-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="421d5-107">Requirements</span></span>  
 <span data-ttu-id="421d5-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="421d5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="421d5-109">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="421d5-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="421d5-110">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="421d5-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="421d5-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="421d5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="421d5-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="421d5-112">See also</span></span>
- [<span data-ttu-id="421d5-113">IGCThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="421d5-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
