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
ms.openlocfilehash: b5f6d7d40274972438a01313bc6aaec475b8e0c6
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805086"
---
# <a name="igcthreadcontrolthreadisblockingforsuspension-method"></a><span data-ttu-id="b8799-102">IGCThreadControl::ThreadIsBlockingForSuspension-Methode</span><span class="sxs-lookup"><span data-stu-id="b8799-102">IGCThreadControl::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="b8799-103">Benachrichtigt den Host, dass der Thread, der den-Befehl aufruft, blockiert wird, möglicherweise für eine Garbage Collection oder eine andere Unterbrechung.</span><span class="sxs-lookup"><span data-stu-id="b8799-103">Notifies the host that the thread that is making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8799-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b8799-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForSuspension ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="b8799-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b8799-105">Remarks</span></span>  
 <span data-ttu-id="b8799-106">Der Host kann innerhalb des `ThreadIsBlockingForSuspension` Rückrufs auswählen, ob ein Thread neu geplant werden soll.</span><span class="sxs-lookup"><span data-stu-id="b8799-106">The host may choose within the `ThreadIsBlockingForSuspension` callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8799-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b8799-107">Requirements</span></span>  
 <span data-ttu-id="b8799-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8799-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8799-109">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="b8799-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b8799-110">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b8799-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b8799-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8799-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8799-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b8799-112">See also</span></span>

- [<span data-ttu-id="b8799-113">IGCThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b8799-113">IGCThreadControl Interface</span></span>](igcthreadcontrol-interface.md)
