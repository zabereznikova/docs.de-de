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
ms.openlocfilehash: 067d4e844055206543e5c7fb409296b0d0a7a549
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134938"
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a><span data-ttu-id="06fde-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger-Methode</span><span class="sxs-lookup"><span data-stu-id="06fde-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger Method</span></span>
<span data-ttu-id="06fde-103">Benachrichtigt den Host, dass der Thread, der diesen Rückruf sendet, innerhalb der Debugdienste blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="06fde-103">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06fde-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="06fde-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="06fde-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="06fde-105">Remarks</span></span>  
 <span data-ttu-id="06fde-106">Die `ThreadIsBlockingForDebugger`-Methode wird immer für einen Lauf Zeit Thread aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="06fde-106">The `ThreadIsBlockingForDebugger` method will always be called on a runtime thread.</span></span>  
  
 <span data-ttu-id="06fde-107">Die `ThreadIsBlockingForDebugger`-Methode bietet dem Host die Möglichkeit, eine andere Aktion auszuführen, während der Thread blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="06fde-107">The `ThreadIsBlockingForDebugger` method gives the host an opportunity to perform another action while the thread blocks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06fde-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="06fde-108">Requirements</span></span>  
 <span data-ttu-id="06fde-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06fde-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06fde-110">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="06fde-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="06fde-111">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="06fde-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="06fde-112">.Net **Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06fde-112">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06fde-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06fde-113">See also</span></span>

- [<span data-ttu-id="06fde-114">IDebuggerThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="06fde-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
