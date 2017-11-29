---
title: IDebuggerThreadControl-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDebuggerThreadControl
api_location: mscoree.dll
api_type: COM
f1_keywords: IDebuggerThreadControl
helpviewer_keywords: IDebuggerThreadControl interface [.NET Framework hosting]
ms.assetid: 0a270c42-a7d1-45f1-a64d-fa3e84d14532
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7e3f8d04a47607958ff5d439b501a6de9bbc5b02
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="idebuggerthreadcontrol-interface"></a><span data-ttu-id="e434b-102">IDebuggerThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e434b-102">IDebuggerThreadControl Interface</span></span>
<span data-ttu-id="e434b-103">Stellt Methoden zum Benachrichtigen des Hosts über die Blockierung und zum Aufheben der Blockierung von Threads von den Debugdiensten bereit.</span><span class="sxs-lookup"><span data-stu-id="e434b-103">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e434b-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="e434b-104">Methods</span></span>  
  
|<span data-ttu-id="e434b-105">Methode</span><span class="sxs-lookup"><span data-stu-id="e434b-105">Method</span></span>|<span data-ttu-id="e434b-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e434b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e434b-107">ThreadIsBlockingForDebugger-Methode</span><span class="sxs-lookup"><span data-stu-id="e434b-107">ThreadIsBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|<span data-ttu-id="e434b-108">Benachrichtigt den Host, dass der Thread, der diesen Rückruf sendet über Block innerhalb der Debugdienste.</span><span class="sxs-lookup"><span data-stu-id="e434b-108">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>|  
|[<span data-ttu-id="e434b-109">ReleaseAllRuntimeThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="e434b-109">ReleaseAllRuntimeThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-releaseallruntimethreads-method.md)|<span data-ttu-id="e434b-110">Benachrichtigt den Host, dass die Debugdienste sind im Begriff, alle Threads freizugeben, die blockiert sind.</span><span class="sxs-lookup"><span data-stu-id="e434b-110">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>|  
|[<span data-ttu-id="e434b-111">StartBlockingForDebugger-Methode</span><span class="sxs-lookup"><span data-stu-id="e434b-111">StartBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-startblockingfordebugger-method.md)|<span data-ttu-id="e434b-112">Benachrichtigt den Host, dass die Debugdienste sind im Begriff, starten die Blockierung aller Threads.</span><span class="sxs-lookup"><span data-stu-id="e434b-112">Notifies the host that the debugging services are about to start blocking all threads.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e434b-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e434b-113">Requirements</span></span>  
 <span data-ttu-id="e434b-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e434b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e434b-115">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e434b-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e434b-116">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e434b-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e434b-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e434b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e434b-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e434b-118">See Also</span></span>  
 [<span data-ttu-id="e434b-119">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e434b-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
