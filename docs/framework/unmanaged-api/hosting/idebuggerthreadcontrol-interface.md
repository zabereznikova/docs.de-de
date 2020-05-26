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
ms.openlocfilehash: 82c6113f4df3334500128df22f7e9ce8d4bf151f
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805278"
---
# <a name="idebuggerthreadcontrol-interface"></a><span data-ttu-id="2466c-102">IDebuggerThreadControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2466c-102">IDebuggerThreadControl Interface</span></span>
<span data-ttu-id="2466c-103">Stellt Methoden bereit, mit denen der Host über die Blockierung und Aufhebung der Blockierung von Threads durch die Debugdienste benachrichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="2466c-103">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2466c-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="2466c-104">Methods</span></span>  
  
|<span data-ttu-id="2466c-105">Methode</span><span class="sxs-lookup"><span data-stu-id="2466c-105">Method</span></span>|<span data-ttu-id="2466c-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2466c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2466c-107">ThreadIsBlockingForDebugger-Methode</span><span class="sxs-lookup"><span data-stu-id="2466c-107">ThreadIsBlockingForDebugger Method</span></span>](idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|<span data-ttu-id="2466c-108">Benachrichtigt den Host, dass der Thread, der diesen Rückruf sendet, innerhalb der Debugdienste blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="2466c-108">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>|  
|[<span data-ttu-id="2466c-109">ReleaseAllRuntimeThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="2466c-109">ReleaseAllRuntimeThreads Method</span></span>](idebuggerthreadcontrol-releaseallruntimethreads-method.md)|<span data-ttu-id="2466c-110">Benachrichtigt den Host, dass die debuggingdienste alle blockierten Threads freigeben.</span><span class="sxs-lookup"><span data-stu-id="2466c-110">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>|  
|[<span data-ttu-id="2466c-111">StartBlockingForDebugger-Methode</span><span class="sxs-lookup"><span data-stu-id="2466c-111">StartBlockingForDebugger Method</span></span>](idebuggerthreadcontrol-startblockingfordebugger-method.md)|<span data-ttu-id="2466c-112">Benachrichtigt den Host, dass die debuggingdienste damit beginnen, alle Threads zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="2466c-112">Notifies the host that the debugging services are about to start blocking all threads.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2466c-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2466c-113">Requirements</span></span>  
 <span data-ttu-id="2466c-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2466c-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2466c-115">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="2466c-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2466c-116">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2466c-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2466c-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2466c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2466c-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2466c-118">See also</span></span>

- [<span data-ttu-id="2466c-119">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="2466c-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
