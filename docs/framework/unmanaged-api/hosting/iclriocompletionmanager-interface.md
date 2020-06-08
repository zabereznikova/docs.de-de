---
title: ICLRIoCompletionManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager
helpviewer_keywords:
- ICLRIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c6c3ace6-e5e7-4450-8cc5-a9a48208c493
topic_type:
- apiref
ms.openlocfilehash: 71afc5e9772f82b922e8f428e6d808e46d092704
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504211"
---
# <a name="iclriocompletionmanager-interface"></a><span data-ttu-id="96aab-102">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="96aab-102">ICLRIoCompletionManager Interface</span></span>
<span data-ttu-id="96aab-103">Implementiert eine Rückruf Methode, die es dem Host ermöglicht, den Common Language Runtime (CLR) über den Status der angegebenen e/a-Anforderungen zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="96aab-103">Implements a callback method that allows the host to notify the common language runtime (CLR) of the status of specified I/O requests.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="96aab-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="96aab-104">Methods</span></span>  
  
|<span data-ttu-id="96aab-105">Methode</span><span class="sxs-lookup"><span data-stu-id="96aab-105">Method</span></span>|<span data-ttu-id="96aab-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="96aab-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="96aab-107">OnComplete-Methode</span><span class="sxs-lookup"><span data-stu-id="96aab-107">OnComplete Method</span></span>](iclriocompletionmanager-oncomplete-method.md)|<span data-ttu-id="96aab-108">Benachrichtigt die CLR über den Status einer e/a-Anforderung, die mithilfe eines Aufrufes der [IHostIoCompletionManager:: Bind](ihostiocompletionmanager-bind-method.md) -Methode durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="96aab-108">Notifies the CLR of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](ihostiocompletionmanager-bind-method.md) method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96aab-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="96aab-109">Remarks</span></span>  
 <span data-ttu-id="96aab-110">Der Host implementiert die e/a-Abschluss Abstraktion mithilfe der [IHostIoCompletionManager](ihostiocompletionmanager-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="96aab-110">The host implements the I/O completion abstraction by using the [IHostIoCompletionManager](ihostiocompletionmanager-interface.md) interface.</span></span> <span data-ttu-id="96aab-111">Die CLR führt e/a-Anforderungen über diese Schnittstelle aus, und der Host benachrichtigt die Laufzeit über das Ergebnis dieser Anforderungen mithilfe der- `ICLRIoCompletionManager` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="96aab-111">The CLR makes I/O requests through this interface, and the host notifies the runtime of the outcome of such requests by using the `ICLRIoCompletionManager` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96aab-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="96aab-112">Requirements</span></span>  
 <span data-ttu-id="96aab-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96aab-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96aab-114">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="96aab-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="96aab-115">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="96aab-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="96aab-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96aab-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96aab-117">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="96aab-117">See also</span></span>

- [<span data-ttu-id="96aab-118">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="96aab-118">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="96aab-119">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="96aab-119">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
- [<span data-ttu-id="96aab-120">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="96aab-120">Hosting Interfaces</span></span>](hosting-interfaces.md)
