---
title: ICorConfiguration::SetDebuggerThreadControl-Methode
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetDebuggerThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetDebuggerThreadControl
helpviewer_keywords:
- SetDebuggerThreadControl method [.NET Framework hosting]
- ICorConfiguration::SetDebuggerThreadControl method [.NET Framework hosting]
ms.assetid: 1ded7639-dacb-4db1-961c-d1ceaec01959
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6fc141cbebe08f8d0974788409d5aef0f68d2878
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59205120"
---
# <a name="icorconfigurationsetdebuggerthreadcontrol-method"></a><span data-ttu-id="e7dcd-102">ICorConfiguration::SetDebuggerThreadControl-Methode</span><span class="sxs-lookup"><span data-stu-id="e7dcd-102">ICorConfiguration::SetDebuggerThreadControl Method</span></span>
<span data-ttu-id="e7dcd-103">Legt die Rückrufschnittstelle, die die Debuggen von Diensten für das Debuggen von aufrufen, wenn die common Language Runtime (CLR) Threads blockiert und freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e7dcd-103">Sets the callback interface that the debugging services will call as common language runtime (CLR) threads are blocked and unblocked for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7dcd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e7dcd-104">Syntax</span></span>  
  
```  
HRESULT SetDebuggerThreadControl (  
    [in] IDebuggerThreadControl* pDebuggerThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7dcd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e7dcd-105">Parameters</span></span>  
 `pDebuggerThreadControl`  
 <span data-ttu-id="e7dcd-106">[in] Ein Zeiger auf ein [IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md) -Objekt, das den Host zu blockieren und Entsperren von Threads von den Debugdiensten benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="e7dcd-106">[in] A pointer to an [IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md) object that notifies the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7dcd-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e7dcd-107">Requirements</span></span>  
 <span data-ttu-id="e7dcd-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7dcd-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7dcd-109">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e7dcd-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e7dcd-110">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e7dcd-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="e7dcd-111">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="e7dcd-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e7dcd-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7dcd-112">See also</span></span>

- [<span data-ttu-id="e7dcd-113">ICorConfiguration-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e7dcd-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
