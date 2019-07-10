---
title: IDebuggerThreadControl::ThreadIsBlockingForDebugger-Methode
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.ThreadIsBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ThreadIsBlockingForDebugger
helpviewer_keywords:
- ThreadIsBlockingForDebugger method [.NET Framework hosting]
- IDebuggerThreadControl::ThreadIsBlockingForDebugger method [.NET Framework hosting]
ms.assetid: d4d7cb2d-69da-48b3-879a-1a8a68c9bfa8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9324e1596913fdafb13239dbefd631cbe3c6ffe4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780491"
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a><span data-ttu-id="e791d-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger-Methode</span><span class="sxs-lookup"><span data-stu-id="e791d-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger Method</span></span>
<span data-ttu-id="e791d-103">Benachrichtigt den Host, die der Thread, der diesen Rückruf sendet Block in der debugging-Diensten.</span><span class="sxs-lookup"><span data-stu-id="e791d-103">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e791d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e791d-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="e791d-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e791d-105">Remarks</span></span>  
 <span data-ttu-id="e791d-106">Die `ThreadIsBlockingForDebugger` Methode wird immer in einem Runtime-Thread aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="e791d-106">The `ThreadIsBlockingForDebugger` method will always be called on a runtime thread.</span></span>  
  
 <span data-ttu-id="e791d-107">Die `ThreadIsBlockingForDebugger` -Methode ermöglicht dem Host eine Möglichkeit zum Ausführen einer anderen Aktion während der Thread blockiert.</span><span class="sxs-lookup"><span data-stu-id="e791d-107">The `ThreadIsBlockingForDebugger` method gives the host an opportunity to perform another action while the thread blocks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e791d-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e791d-108">Requirements</span></span>  
 <span data-ttu-id="e791d-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e791d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e791d-110">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e791d-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e791d-111">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e791d-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e791d-112">**NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e791d-112">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e791d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e791d-113">See also</span></span>

- [<span data-ttu-id="e791d-114">IDebuggerThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e791d-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
