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
ms.openlocfilehash: 8c2741d7db60781fef12293f3be0b515a55b7885
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705508"
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a><span data-ttu-id="df261-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger-Methode</span><span class="sxs-lookup"><span data-stu-id="df261-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger Method</span></span>

<span data-ttu-id="df261-103">Benachrichtigt den Host, dass der Thread, der diesen Rückruf sendet, innerhalb der Debugdienste blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="df261-103">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df261-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="df261-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="df261-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="df261-105">Remarks</span></span>  

 <span data-ttu-id="df261-106">Die- `ThreadIsBlockingForDebugger` Methode wird immer in einem Lauf Zeit Thread aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="df261-106">The `ThreadIsBlockingForDebugger` method will always be called on a runtime thread.</span></span>  
  
 <span data-ttu-id="df261-107">Die- `ThreadIsBlockingForDebugger` Methode gibt dem Host die Möglichkeit, eine andere Aktion auszuführen, während der Thread blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="df261-107">The `ThreadIsBlockingForDebugger` method gives the host an opportunity to perform another action while the thread blocks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df261-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="df261-108">Requirements</span></span>  

 <span data-ttu-id="df261-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df261-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df261-110">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="df261-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="df261-111">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="df261-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="df261-112">.Net **Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df261-112">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df261-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="df261-113">See also</span></span>

- [<span data-ttu-id="df261-114">IDebuggerThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="df261-114">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)
