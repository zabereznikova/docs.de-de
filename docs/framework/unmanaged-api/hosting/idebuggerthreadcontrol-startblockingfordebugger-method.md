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
ms.openlocfilehash: 878dba37728734a777d2f95226b60bfbe9aae16a
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805269"
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="99548-102">IDebuggerThreadControl::StartBlockingForDebugger-Methode</span><span class="sxs-lookup"><span data-stu-id="99548-102">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>
<span data-ttu-id="99548-103">Benachrichtigt den Host, dass die debuggingdienste damit beginnen, alle Threads zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="99548-103">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99548-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="99548-104">Syntax</span></span>  
  
```cpp  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99548-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="99548-105">Parameters</span></span>  
 `dwUnused`  
 <span data-ttu-id="99548-106">[in] Reserviert für zukünftige Verwendung.</span><span class="sxs-lookup"><span data-stu-id="99548-106">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99548-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="99548-107">Remarks</span></span>  
 <span data-ttu-id="99548-108">Die- `StartBlockingForDebugger` Methode kann in einem Lauf Zeit Thread aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="99548-108">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99548-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="99548-109">Requirements</span></span>  
 <span data-ttu-id="99548-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99548-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99548-111">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="99548-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="99548-112">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="99548-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="99548-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99548-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99548-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="99548-114">See also</span></span>

- [<span data-ttu-id="99548-115">IDebuggerThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="99548-115">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)
