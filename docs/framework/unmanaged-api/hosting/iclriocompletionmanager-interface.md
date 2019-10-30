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
ms.openlocfilehash: b63d4269a8d48ee49016a4c51d63bf81bdba8da2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141027"
---
# <a name="iclriocompletionmanager-interface"></a><span data-ttu-id="9af74-102">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9af74-102">ICLRIoCompletionManager Interface</span></span>
<span data-ttu-id="9af74-103">Implementiert eine Rückruf Methode, die es dem Host ermöglicht, den Common Language Runtime (CLR) über den Status der angegebenen e/a-Anforderungen zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="9af74-103">Implements a callback method that allows the host to notify the common language runtime (CLR) of the status of specified I/O requests.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9af74-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="9af74-104">Methods</span></span>  
  
|<span data-ttu-id="9af74-105">Methode</span><span class="sxs-lookup"><span data-stu-id="9af74-105">Method</span></span>|<span data-ttu-id="9af74-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9af74-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9af74-107">OnComplete-Methode</span><span class="sxs-lookup"><span data-stu-id="9af74-107">OnComplete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|<span data-ttu-id="9af74-108">Benachrichtigt die CLR über den Status einer e/a-Anforderung, die mithilfe eines Aufrufes der [IHostIoCompletionManager:: Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) -Methode durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="9af74-108">Notifies the CLR of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9af74-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9af74-109">Remarks</span></span>  
 <span data-ttu-id="9af74-110">Der Host implementiert die e/a-Abschluss Abstraktion mithilfe der [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="9af74-110">The host implements the I/O completion abstraction by using the [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) interface.</span></span> <span data-ttu-id="9af74-111">Die CLR führt e/a-Anforderungen über diese Schnittstelle aus, und der Host benachrichtigt die Laufzeit über das Ergebnis dieser Anforderungen mithilfe der `ICLRIoCompletionManager`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="9af74-111">The CLR makes I/O requests through this interface, and the host notifies the runtime of the outcome of such requests by using the `ICLRIoCompletionManager` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9af74-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9af74-112">Requirements</span></span>  
 <span data-ttu-id="9af74-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9af74-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9af74-114">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="9af74-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9af74-115">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9af74-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9af74-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9af74-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9af74-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9af74-117">See also</span></span>

- [<span data-ttu-id="9af74-118">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9af74-118">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="9af74-119">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9af74-119">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
- [<span data-ttu-id="9af74-120">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9af74-120">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
