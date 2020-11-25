---
title: IDebuggerThreadControl::StartBlockingForDebugger-Methode
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.StartBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StartBlockingForDebugger
helpviewer_keywords:
- IDebuggerThreadControl::StartBlockingForDebugger method [.NET Framework hosting]
- StartBlockingForDebugger method [.NET Framework hosting]
ms.assetid: 5c8f11b4-35d3-4c39-9bbd-58b896ba5ba6
topic_type:
- apiref
ms.openlocfilehash: 1e0cb52a6b9f03209256e5398415b4ec632fb5e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705504"
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="3ffd0-102">IDebuggerThreadControl::StartBlockingForDebugger-Methode</span><span class="sxs-lookup"><span data-stu-id="3ffd0-102">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>

<span data-ttu-id="3ffd0-103">Benachrichtigt den Host, dass die debuggingdienste damit beginnen, alle Threads zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="3ffd0-103">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ffd0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3ffd0-104">Syntax</span></span>  
  
```cpp  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ffd0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3ffd0-105">Parameters</span></span>  

 `dwUnused`  
 <span data-ttu-id="3ffd0-106">[in] Reserviert für zukünftige Verwendung.</span><span class="sxs-lookup"><span data-stu-id="3ffd0-106">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ffd0-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3ffd0-107">Remarks</span></span>  

 <span data-ttu-id="3ffd0-108">Die- `StartBlockingForDebugger` Methode kann in einem Lauf Zeit Thread aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3ffd0-108">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ffd0-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3ffd0-109">Requirements</span></span>  

 <span data-ttu-id="3ffd0-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ffd0-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ffd0-111">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="3ffd0-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3ffd0-112">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3ffd0-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3ffd0-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ffd0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ffd0-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3ffd0-114">See also</span></span>

- [<span data-ttu-id="3ffd0-115">IDebuggerThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3ffd0-115">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)
