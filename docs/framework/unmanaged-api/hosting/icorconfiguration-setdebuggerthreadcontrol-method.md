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
ms.openlocfilehash: 449546a0f774a241efd035190d43de103199edbf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436805"
---
# <a name="icorconfigurationsetdebuggerthreadcontrol-method"></a><span data-ttu-id="2acef-102">ICorConfiguration::SetDebuggerThreadControl-Methode</span><span class="sxs-lookup"><span data-stu-id="2acef-102">ICorConfiguration::SetDebuggerThreadControl Method</span></span>
<span data-ttu-id="2acef-103">Legt die Rückrufschnittstelle, die der Debugdienste für das Debuggen aufrufen, wenn die common Language Runtime (CLR)-Threads blockiert und freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2acef-103">Sets the callback interface that the debugging services will call as common language runtime (CLR) threads are blocked and unblocked for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2acef-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2acef-104">Syntax</span></span>  
  
```  
HRESULT SetDebuggerThreadControl (  
    [in] IDebuggerThreadControl* pDebuggerThreadControl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2acef-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2acef-105">Parameters</span></span>  
 `pDebuggerThreadControl`  
 <span data-ttu-id="2acef-106">[in] Ein Zeiger auf ein [IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md) -Objekt, das den Host zu blockieren und zum Aufheben der Blockierung von Threads von den Debugdiensten benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="2acef-106">[in] A pointer to an [IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md) object that notifies the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2acef-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2acef-107">Requirements</span></span>  
 <span data-ttu-id="2acef-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2acef-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2acef-109">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2acef-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2acef-110">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2acef-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2acef-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2acef-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2acef-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2acef-112">See Also</span></span>  
 [<span data-ttu-id="2acef-113">ICorConfiguration-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2acef-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
