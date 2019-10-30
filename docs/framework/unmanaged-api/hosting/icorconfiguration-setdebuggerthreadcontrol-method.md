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
ms.openlocfilehash: 0f6a369691ab2e4e9fd2e5d9731fb1dc0a42ba11
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127796"
---
# <a name="icorconfigurationsetdebuggerthreadcontrol-method"></a><span data-ttu-id="40dd8-102">ICorConfiguration::SetDebuggerThreadControl-Methode</span><span class="sxs-lookup"><span data-stu-id="40dd8-102">ICorConfiguration::SetDebuggerThreadControl Method</span></span>
<span data-ttu-id="40dd8-103">Legt die Rückruf Schnittstelle fest, die von den Debugdiensten aufgerufen wird, wenn Common Language Runtime (CLR)-Threads blockiert und für das Debuggen aufgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="40dd8-103">Sets the callback interface that the debugging services will call as common language runtime (CLR) threads are blocked and unblocked for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40dd8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="40dd8-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDebuggerThreadControl (  
    [in] IDebuggerThreadControl* pDebuggerThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40dd8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="40dd8-105">Parameters</span></span>  
 `pDebuggerThreadControl`  
 <span data-ttu-id="40dd8-106">in Ein Zeiger auf ein [IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md) -Objekt, das den Host über die Blockierung und Aufhebung der Blockierung von Threads durch die Debugdienste benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="40dd8-106">[in] A pointer to an [IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md) object that notifies the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40dd8-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="40dd8-107">Requirements</span></span>  
 <span data-ttu-id="40dd8-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40dd8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40dd8-109">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="40dd8-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="40dd8-110">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="40dd8-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="40dd8-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40dd8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40dd8-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40dd8-112">See also</span></span>

- [<span data-ttu-id="40dd8-113">ICorConfiguration-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="40dd8-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
