---
title: IDebuggerThreadControl-Schnittstelle
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IDebuggerThreadControl
helpviewer_keywords:
- IDebuggerThreadControl interface [.NET Framework hosting]
ms.assetid: 0a270c42-a7d1-45f1-a64d-fa3e84d14532
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a551d3cc6ab3dd3887f232018f8201de4036d1b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096835"
---
# <a name="idebuggerthreadcontrol-interface"></a><span data-ttu-id="1fb8c-102">IDebuggerThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1fb8c-102">IDebuggerThreadControl Interface</span></span>
<span data-ttu-id="1fb8c-103">Stellt Methoden zum Benachrichtigen des Hosts über das Blockieren und Entsperren von Threads von den Debugdiensten.</span><span class="sxs-lookup"><span data-stu-id="1fb8c-103">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1fb8c-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="1fb8c-104">Methods</span></span>  
  
|<span data-ttu-id="1fb8c-105">Methode</span><span class="sxs-lookup"><span data-stu-id="1fb8c-105">Method</span></span>|<span data-ttu-id="1fb8c-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1fb8c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1fb8c-107">ThreadIsBlockingForDebugger-Methode</span><span class="sxs-lookup"><span data-stu-id="1fb8c-107">ThreadIsBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|<span data-ttu-id="1fb8c-108">Benachrichtigt den Host, die der Thread, der diesen Rückruf sendet Block in der debugging-Diensten.</span><span class="sxs-lookup"><span data-stu-id="1fb8c-108">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>|  
|[<span data-ttu-id="1fb8c-109">ReleaseAllRuntimeThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="1fb8c-109">ReleaseAllRuntimeThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-releaseallruntimethreads-method.md)|<span data-ttu-id="1fb8c-110">Benachrichtigt den Host, dass die Debuggen von Diensten sind im Begriff, die alle Threads freigegeben, die blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="1fb8c-110">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>|  
|[<span data-ttu-id="1fb8c-111">StartBlockingForDebugger-Methode</span><span class="sxs-lookup"><span data-stu-id="1fb8c-111">StartBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-startblockingfordebugger-method.md)|<span data-ttu-id="1fb8c-112">Benachrichtigt den Host, dass die Debuggen von Diensten zu beginnen, alle Threads blockiert sind.</span><span class="sxs-lookup"><span data-stu-id="1fb8c-112">Notifies the host that the debugging services are about to start blocking all threads.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1fb8c-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1fb8c-113">Requirements</span></span>  
 <span data-ttu-id="1fb8c-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1fb8c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fb8c-115">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1fb8c-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1fb8c-116">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1fb8c-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1fb8c-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fb8c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fb8c-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1fb8c-118">See also</span></span>

- [<span data-ttu-id="1fb8c-119">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1fb8c-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
