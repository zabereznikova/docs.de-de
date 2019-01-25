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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aa2872fec7765f38fba9589a6fab659e73131937
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54620460"
---
# <a name="igcthreadcontrolthreadisblockingforsuspension-method"></a><span data-ttu-id="b8dbc-102">IGCThreadControl::ThreadIsBlockingForSuspension-Methode</span><span class="sxs-lookup"><span data-stu-id="b8dbc-102">IGCThreadControl::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="b8dbc-103">Benachrichtigt den Host an, dass der Thread, der den Aufruf ausgeführt hat zu blockieren, z. B. für eine Garbagecollection oder einer anderen Unterbrechung.</span><span class="sxs-lookup"><span data-stu-id="b8dbc-103">Notifies the host that the thread that is making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8dbc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b8dbc-104">Syntax</span></span>  
  
```  
HRESULT ThreadIsBlockingForSuspension ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="b8dbc-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b8dbc-105">Remarks</span></span>  
 <span data-ttu-id="b8dbc-106">Der Host kann wählen, in der `ThreadIsBlockingForSuspension` Rückruf an, ob ein Thread verlegt.</span><span class="sxs-lookup"><span data-stu-id="b8dbc-106">The host may choose within the `ThreadIsBlockingForSuspension` callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8dbc-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b8dbc-107">Requirements</span></span>  
 <span data-ttu-id="b8dbc-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8dbc-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8dbc-109">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b8dbc-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b8dbc-110">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b8dbc-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b8dbc-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8dbc-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8dbc-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8dbc-112">See also</span></span>
- [<span data-ttu-id="b8dbc-113">IGCThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b8dbc-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
