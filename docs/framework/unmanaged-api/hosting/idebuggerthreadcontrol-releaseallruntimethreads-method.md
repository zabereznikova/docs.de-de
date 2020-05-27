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
ms.openlocfilehash: 50ffb33456f942a71089f9bc44daa07f6b77ab21
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805298"
---
# <a name="idebuggerthreadcontrolreleaseallruntimethreads-method"></a><span data-ttu-id="343bc-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="343bc-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads Method</span></span>
<span data-ttu-id="343bc-103">Benachrichtigt den Host, dass die debuggingdienste alle blockierten Threads freigeben.</span><span class="sxs-lookup"><span data-stu-id="343bc-103">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="343bc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="343bc-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleaseAllRuntimeThreads ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="343bc-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="343bc-105">Remarks</span></span>  
 <span data-ttu-id="343bc-106">Die- `ReleaseAllRuntimeThreads` Methode wird nie für einen Lauf Zeit Thread aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="343bc-106">The `ReleaseAllRuntimeThreads` method will never be called on a runtime thread.</span></span> <span data-ttu-id="343bc-107">Wenn für den Host ein Laufzeitthread blockiert ist, sollte er jetzt freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="343bc-107">If the host has a runtime thread blocked, it should release it now.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="343bc-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="343bc-108">Requirements</span></span>  
 <span data-ttu-id="343bc-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="343bc-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="343bc-110">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="343bc-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="343bc-111">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="343bc-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="343bc-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="343bc-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="343bc-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="343bc-113">See also</span></span>

- [<span data-ttu-id="343bc-114">IDebuggerThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="343bc-114">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)
