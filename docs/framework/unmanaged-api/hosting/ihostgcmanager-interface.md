---
title: IHostGCManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager
helpviewer_keywords:
- IHostGCManager interface [.NET Framework hosting]
ms.assetid: 820330a4-244c-4f67-ab5e-f24b0b3c2080
topic_type:
- apiref
ms.openlocfilehash: 428e4cf8997713b08e40d9376c34ae5eee8cfa32
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804853"
---
# <a name="ihostgcmanager-interface"></a><span data-ttu-id="53111-102">IHostGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="53111-102">IHostGCManager Interface</span></span>
<span data-ttu-id="53111-103">Stellt Methoden bereit, die den Host von Ereignissen in dem Garbage Collection Mechanismus benachrichtigen, der vom Common Language Runtime (CLR) implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="53111-103">Provides methods that notify the host of events in the garbage collection mechanism implemented by the common language runtime (CLR).</span></span>  
  
## <a name="members"></a><span data-ttu-id="53111-104">Member</span><span class="sxs-lookup"><span data-stu-id="53111-104">Members</span></span>  
  
|<span data-ttu-id="53111-105">Member</span><span class="sxs-lookup"><span data-stu-id="53111-105">Member</span></span>|<span data-ttu-id="53111-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="53111-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="53111-107">SuspensionEnding-Methode</span><span class="sxs-lookup"><span data-stu-id="53111-107">SuspensionEnding Method</span></span>](ihostgcmanager-suspensionending-method.md)|<span data-ttu-id="53111-108">Benachrichtigt den Host, dass die CLR die Ausführung von Tasks auf Threads fortsetzt, die für eine Garbage Collection angehalten wurden.</span><span class="sxs-lookup"><span data-stu-id="53111-108">Notifies the host that the CLR is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>|  
|[<span data-ttu-id="53111-109">SuspensionStarting-Methode</span><span class="sxs-lookup"><span data-stu-id="53111-109">SuspensionStarting Method</span></span>](ihostgcmanager-suspensionstarting-method.md)|<span data-ttu-id="53111-110">Benachrichtigt den Host, dass die CLR die Ausführung von Tasks unterteilt, um eine Garbage Collection auszuführen.</span><span class="sxs-lookup"><span data-stu-id="53111-110">Notifies the host that the CLR is suspending execution of tasks, to perform a garbage collection.</span></span>|  
|[<span data-ttu-id="53111-111">ThreadIsBlockingForSuspension-Methode</span><span class="sxs-lookup"><span data-stu-id="53111-111">ThreadIsBlockingForSuspension Method</span></span>](ihostgcmanager-threadisblockingforsuspension-method.md)|<span data-ttu-id="53111-112">Benachrichtigt den Host, dass der Thread, von dem der Methoden aufrufging, für eine Garbage Collection blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="53111-112">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="53111-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="53111-113">Requirements</span></span>  
 <span data-ttu-id="53111-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53111-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53111-115">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="53111-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="53111-116">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="53111-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="53111-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53111-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53111-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="53111-118">See also</span></span>

- [<span data-ttu-id="53111-119">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="53111-119">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="53111-120">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="53111-120">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="53111-121">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="53111-121">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="53111-122">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="53111-122">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="53111-123">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="53111-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
