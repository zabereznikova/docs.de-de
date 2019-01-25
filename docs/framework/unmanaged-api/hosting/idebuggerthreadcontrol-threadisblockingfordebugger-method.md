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
ms.openlocfilehash: aa72c136e98f80df6d2868c447e1c535ae61af06
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54739627"
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a><span data-ttu-id="613e4-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger-Methode</span><span class="sxs-lookup"><span data-stu-id="613e4-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger Method</span></span>
<span data-ttu-id="613e4-103">Benachrichtigt den Host, die der Thread, der diesen Rückruf sendet Block in der debugging-Diensten.</span><span class="sxs-lookup"><span data-stu-id="613e4-103">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="613e4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="613e4-104">Syntax</span></span>  
  
```  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="613e4-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="613e4-105">Remarks</span></span>  
 <span data-ttu-id="613e4-106">Die `ThreadIsBlockingForDebugger` Methode wird immer in einem Runtime-Thread aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="613e4-106">The `ThreadIsBlockingForDebugger` method will always be called on a runtime thread.</span></span>  
  
 <span data-ttu-id="613e4-107">Die `ThreadIsBlockingForDebugger` -Methode ermöglicht dem Host eine Möglichkeit zum Ausführen einer anderen Aktion während der Thread blockiert.</span><span class="sxs-lookup"><span data-stu-id="613e4-107">The `ThreadIsBlockingForDebugger` method gives the host an opportunity to perform another action while the thread blocks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="613e4-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="613e4-108">Requirements</span></span>  
 <span data-ttu-id="613e4-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="613e4-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="613e4-110">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="613e4-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="613e4-111">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="613e4-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="613e4-112">**NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="613e4-112">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="613e4-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="613e4-113">See also</span></span>
- [<span data-ttu-id="613e4-114">IDebuggerThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="613e4-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
