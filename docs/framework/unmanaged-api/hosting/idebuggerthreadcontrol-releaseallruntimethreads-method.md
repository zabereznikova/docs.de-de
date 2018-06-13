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
ms.openlocfilehash: 5b3623c886a48cc938be017f955fbdac1df3f10f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437634"
---
# <a name="idebuggerthreadcontrolreleaseallruntimethreads-method"></a><span data-ttu-id="0d088-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="0d088-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads Method</span></span>
<span data-ttu-id="0d088-103">Benachrichtigt den Host, dass die Debugdienste sind im Begriff, alle Threads freizugeben, die blockiert sind.</span><span class="sxs-lookup"><span data-stu-id="0d088-103">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d088-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0d088-104">Syntax</span></span>  
  
```  
HRESULT ReleaseAllRuntimeThreads ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="0d088-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0d088-105">Remarks</span></span>  
 <span data-ttu-id="0d088-106">Die `ReleaseAllRuntimeThreads` Methode wird nie in einem Runtime-Thread aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0d088-106">The `ReleaseAllRuntimeThreads` method will never be called on a runtime thread.</span></span> <span data-ttu-id="0d088-107">Der Host einen Common Language Runtime-Thread blockiert ist, sollten sie es jetzt freigeben.</span><span class="sxs-lookup"><span data-stu-id="0d088-107">If the host has a runtime thread blocked, it should release it now.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d088-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0d088-108">Requirements</span></span>  
 <span data-ttu-id="0d088-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d088-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d088-110">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0d088-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0d088-111">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0d088-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0d088-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d088-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d088-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0d088-113">See Also</span></span>  
 [<span data-ttu-id="0d088-114">IDebuggerThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0d088-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
