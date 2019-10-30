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
ms.openlocfilehash: f43ee6d9a3832fca1766ec27c9f02d1aab2f5b8d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127773"
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a><span data-ttu-id="661e5-102">ICorConfiguration::SetGCThreadControl-Methode</span><span class="sxs-lookup"><span data-stu-id="661e5-102">ICorConfiguration::SetGCThreadControl Method</span></span>
<span data-ttu-id="661e5-103">Legt die Rückruf Schnittstelle für das Planen von Threads für nicht-Lauf Zeit Aufgaben fest, die andernfalls für eine Garbage Collection blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="661e5-103">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="661e5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="661e5-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="661e5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="661e5-105">Parameters</span></span>  
 `pGCThreadControl`  
 <span data-ttu-id="661e5-106">in Ein Zeiger auf ein [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md) -Objekt, das den Host über die Unterbrechung von Threads für nicht-Lauf Zeit Aufgaben benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="661e5-106">[in] A pointer to an [IGCThreadControl](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md) object that notifies the host about the suspension of threads for non-runtime tasks.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="661e5-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="661e5-107">Remarks</span></span>  
 <span data-ttu-id="661e5-108">Der Host kann im [IGCThreadControl:: ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md) -Rückruf auswählen, ob ein Thread neu geplant werden soll.</span><span class="sxs-lookup"><span data-stu-id="661e5-108">The host may choose within the [IGCThreadControl::ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-threadisblockingforsuspension-method.md) callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="661e5-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="661e5-109">Requirements</span></span>  
 <span data-ttu-id="661e5-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="661e5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="661e5-111">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="661e5-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="661e5-112">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="661e5-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="661e5-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="661e5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="661e5-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="661e5-114">See also</span></span>

- [<span data-ttu-id="661e5-115">ICorConfiguration-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="661e5-115">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
