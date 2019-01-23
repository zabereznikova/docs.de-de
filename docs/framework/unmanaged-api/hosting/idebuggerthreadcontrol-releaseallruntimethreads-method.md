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
ms.openlocfilehash: a5e2501a5ab62c6aaef2b3f754f9eed10e4e4b97
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505021"
---
# <a name="idebuggerthreadcontrolreleaseallruntimethreads-method"></a><span data-ttu-id="33260-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="33260-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads Method</span></span>
<span data-ttu-id="33260-103">Benachrichtigt den Host, dass die Debuggen von Diensten sind im Begriff, die alle Threads freigegeben, die blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="33260-103">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33260-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="33260-104">Syntax</span></span>  
  
```  
HRESULT ReleaseAllRuntimeThreads ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="33260-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="33260-105">Remarks</span></span>  
 <span data-ttu-id="33260-106">Die `ReleaseAllRuntimeThreads` Methode nie in einem Runtime-Thread aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="33260-106">The `ReleaseAllRuntimeThreads` method will never be called on a runtime thread.</span></span> <span data-ttu-id="33260-107">Wenn der Host einen Common Language Runtime-Thread blockiert ist, sollte er es jetzt freigeben.</span><span class="sxs-lookup"><span data-stu-id="33260-107">If the host has a runtime thread blocked, it should release it now.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33260-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="33260-108">Requirements</span></span>  
 <span data-ttu-id="33260-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33260-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33260-110">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="33260-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="33260-111">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="33260-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="33260-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33260-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33260-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33260-113">See also</span></span>
- [<span data-ttu-id="33260-114">IDebuggerThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="33260-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
