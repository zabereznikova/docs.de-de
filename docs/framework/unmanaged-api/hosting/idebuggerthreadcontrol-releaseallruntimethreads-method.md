---
title: IDebuggerThreadControl::ReleaseAllRuntimeThreads-Methode
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.ReleaseAllRuntimeThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ReleaseAllRuntimeThreads
helpviewer_keywords:
- ReleaseAllRuntimeThreads method [.NET Framework hosting]
- IDebuggerThreadControl::ReleaseAllRuntimeThreads method [.NET Framework hosting]
ms.assetid: 1a2995ff-5f02-4b49-84dc-3a5f9cfd7d55
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 136dab5c05c310d85a5e18bcdc6da0de901d3ace
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59227469"
---
# <a name="idebuggerthreadcontrolreleaseallruntimethreads-method"></a><span data-ttu-id="01050-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="01050-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads Method</span></span>
<span data-ttu-id="01050-103">Benachrichtigt den Host, dass die Debuggen von Diensten sind im Begriff, die alle Threads freigegeben, die blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="01050-103">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01050-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="01050-104">Syntax</span></span>  
  
```  
HRESULT ReleaseAllRuntimeThreads ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="01050-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="01050-105">Remarks</span></span>  
 <span data-ttu-id="01050-106">Die `ReleaseAllRuntimeThreads` Methode nie in einem Runtime-Thread aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="01050-106">The `ReleaseAllRuntimeThreads` method will never be called on a runtime thread.</span></span> <span data-ttu-id="01050-107">Wenn der Host einen Common Language Runtime-Thread blockiert ist, sollte er es jetzt freigeben.</span><span class="sxs-lookup"><span data-stu-id="01050-107">If the host has a runtime thread blocked, it should release it now.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01050-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="01050-108">Requirements</span></span>  
 <span data-ttu-id="01050-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01050-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01050-110">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="01050-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="01050-111">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="01050-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="01050-112">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="01050-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="01050-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01050-113">See also</span></span>

- [<span data-ttu-id="01050-114">IDebuggerThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="01050-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
