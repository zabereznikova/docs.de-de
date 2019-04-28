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
ms.openlocfilehash: 47ff178cc9ab798593848e56fc7bba8ac82ae295
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699694"
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a><span data-ttu-id="6afcd-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger-Methode</span><span class="sxs-lookup"><span data-stu-id="6afcd-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger Method</span></span>
<span data-ttu-id="6afcd-103">Benachrichtigt den Host, die der Thread, der diesen Rückruf sendet Block in der debugging-Diensten.</span><span class="sxs-lookup"><span data-stu-id="6afcd-103">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6afcd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6afcd-104">Syntax</span></span>  
  
```  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="6afcd-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6afcd-105">Remarks</span></span>  
 <span data-ttu-id="6afcd-106">Die `ThreadIsBlockingForDebugger` Methode wird immer in einem Runtime-Thread aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="6afcd-106">The `ThreadIsBlockingForDebugger` method will always be called on a runtime thread.</span></span>  
  
 <span data-ttu-id="6afcd-107">Die `ThreadIsBlockingForDebugger` -Methode ermöglicht dem Host eine Möglichkeit zum Ausführen einer anderen Aktion während der Thread blockiert.</span><span class="sxs-lookup"><span data-stu-id="6afcd-107">The `ThreadIsBlockingForDebugger` method gives the host an opportunity to perform another action while the thread blocks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6afcd-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6afcd-108">Requirements</span></span>  
 <span data-ttu-id="6afcd-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6afcd-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6afcd-110">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6afcd-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6afcd-111">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6afcd-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6afcd-112">**NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6afcd-112">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6afcd-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6afcd-113">See also</span></span>

- [<span data-ttu-id="6afcd-114">IDebuggerThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6afcd-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
