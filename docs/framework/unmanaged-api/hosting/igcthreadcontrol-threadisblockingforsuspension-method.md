---
title: IGCThreadControl::ThreadIsBlockingForSuspension-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCThreadControl.ThreadIsBlockingForSuspension
api_location: mscoree.dll
api_type: COM
f1_keywords: ThreadIsBlockingForSuspension
helpviewer_keywords:
- IGCThreadControl::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: ed5b5b58-7db7-46b5-9e2c-278db7159cee
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 815ed06cb5772e7d04002f9d0d31bd971f2d345a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="igcthreadcontrolthreadisblockingforsuspension-method"></a><span data-ttu-id="127db-102">IGCThreadControl::ThreadIsBlockingForSuspension-Methode</span><span class="sxs-lookup"><span data-stu-id="127db-102">IGCThreadControl::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="127db-103">Benachrichtigt den Host, dass der Thread, der den Aufruf ausgeführt hat zu blockieren, möglicherweise für eine Garbagecollection oder eine andere Unterbrechung ist.</span><span class="sxs-lookup"><span data-stu-id="127db-103">Notifies the host that the thread that is making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="127db-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="127db-104">Syntax</span></span>  
  
```  
HRESULT ThreadIsBlockingForSuspension ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="127db-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="127db-105">Remarks</span></span>  
 <span data-ttu-id="127db-106">Der Host kann wählen, in der `ThreadIsBlockingForSuspension` Rückruf an, ob ein Thread verlegt.</span><span class="sxs-lookup"><span data-stu-id="127db-106">The host may choose within the `ThreadIsBlockingForSuspension` callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="127db-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="127db-107">Requirements</span></span>  
 <span data-ttu-id="127db-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="127db-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="127db-109">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="127db-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="127db-110">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="127db-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="127db-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="127db-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="127db-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="127db-112">See Also</span></span>  
 [<span data-ttu-id="127db-113">IGCThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="127db-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
