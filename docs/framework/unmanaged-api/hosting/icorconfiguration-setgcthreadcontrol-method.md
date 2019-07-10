---
title: ICorConfiguration::SetGCThreadControl-Methode
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCThreadControl
helpviewer_keywords:
- ICorConfiguration::SetGCThreadControl method [.NET Framework hosting]
- SetGCThreadControl method [.NET Framework hosting]
ms.assetid: 72e38e61-3d56-4ae3-b8f6-0ab7922aaf11
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 93b52e0faef0fa3cc22283d6b46c5fe5153c3eb2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779866"
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a><span data-ttu-id="c6565-102">ICorConfiguration::SetGCThreadControl-Methode</span><span class="sxs-lookup"><span data-stu-id="c6565-102">ICorConfiguration::SetGCThreadControl Method</span></span>
<span data-ttu-id="c6565-103">Legt die Rückrufschnittstelle für die Planung von Threads für nicht-Runtime-Aufgaben, die für eine Garbagecollection andernfalls blockiert würden.</span><span class="sxs-lookup"><span data-stu-id="c6565-103">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6565-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c6565-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6565-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c6565-105">Parameters</span></span>  
 `pGCThreadControl`  
 <span data-ttu-id="c6565-106">[in] Ein Zeiger auf ein [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md) -Objekt, das den Host über das Anhalten des Threads für Laufzeitaufgaben benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="c6565-106">[in] A pointer to an [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md) object that notifies the host about the suspension of threads for non-runtime tasks.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6565-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c6565-107">Remarks</span></span>  
 <span data-ttu-id="c6565-108">Der Host kann wählen, in der [IGCThreadControl:: ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md) Rückruf an, ob ein Thread verlegt.</span><span class="sxs-lookup"><span data-stu-id="c6565-108">The host may choose within the [IGCThreadControl::ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md) callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6565-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c6565-109">Requirements</span></span>  
 <span data-ttu-id="c6565-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6565-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6565-111">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c6565-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c6565-112">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c6565-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c6565-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6565-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6565-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6565-114">See also</span></span>

- [<span data-ttu-id="c6565-115">ICorConfiguration-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c6565-115">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
