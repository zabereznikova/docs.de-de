---
title: IGCThreadControl::ThreadIsBlockingForSuspension-Methode
ms.date: 03/30/2017
api_name:
- IGCThreadControl.ThreadIsBlockingForSuspension
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ThreadIsBlockingForSuspension
helpviewer_keywords:
- IGCThreadControl::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: ed5b5b58-7db7-46b5-9e2c-278db7159cee
topic_type:
- apiref
ms.openlocfilehash: 39834ba868a21ead3113f2f0d9157cd210d9798c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721646"
---
# <a name="igcthreadcontrolthreadisblockingforsuspension-method"></a><span data-ttu-id="33528-102">IGCThreadControl::ThreadIsBlockingForSuspension-Methode</span><span class="sxs-lookup"><span data-stu-id="33528-102">IGCThreadControl::ThreadIsBlockingForSuspension Method</span></span>

<span data-ttu-id="33528-103">Benachrichtigt den Host, dass der Thread, der den-Befehl aufruft, blockiert wird, möglicherweise für eine Garbage Collection oder eine andere Unterbrechung.</span><span class="sxs-lookup"><span data-stu-id="33528-103">Notifies the host that the thread that is making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33528-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="33528-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForSuspension ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="33528-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="33528-105">Remarks</span></span>  

 <span data-ttu-id="33528-106">Der Host kann innerhalb des `ThreadIsBlockingForSuspension` Rückrufs auswählen, ob ein Thread neu geplant werden soll.</span><span class="sxs-lookup"><span data-stu-id="33528-106">The host may choose within the `ThreadIsBlockingForSuspension` callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33528-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="33528-107">Requirements</span></span>  

 <span data-ttu-id="33528-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33528-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33528-109">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="33528-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="33528-110">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="33528-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="33528-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33528-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33528-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="33528-112">See also</span></span>

- [<span data-ttu-id="33528-113">IGCThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="33528-113">IGCThreadControl Interface</span></span>](igcthreadcontrol-interface.md)
