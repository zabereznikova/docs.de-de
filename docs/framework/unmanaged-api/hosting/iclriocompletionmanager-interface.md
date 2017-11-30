---
title: ICLRIoCompletionManager-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRIoCompletionManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRIoCompletionManager
helpviewer_keywords: ICLRIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c6c3ace6-e5e7-4450-8cc5-a9a48208c493
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dbff3c39da2a18ab45f0ea03d1e1588aa61c7c3c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclriocompletionmanager-interface"></a><span data-ttu-id="d2421-102">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d2421-102">ICLRIoCompletionManager Interface</span></span>
<span data-ttu-id="d2421-103">Implementiert fordert eine Rückrufmethode, die den Host zu benachrichtigen, die common Language Runtime (CLR) den Status der angegebenen e/a ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="d2421-103">Implements a callback method that allows the host to notify the common language runtime (CLR) of the status of specified I/O requests.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d2421-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="d2421-104">Methods</span></span>  
  
|<span data-ttu-id="d2421-105">Methode</span><span class="sxs-lookup"><span data-stu-id="d2421-105">Method</span></span>|<span data-ttu-id="d2421-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d2421-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d2421-107">OnComplete-Methode</span><span class="sxs-lookup"><span data-stu-id="d2421-107">OnComplete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|<span data-ttu-id="d2421-108">Benachrichtigt die CLR über den Status einer e/a-Anforderung, die erstellt wurde, mithilfe eines Aufrufs an die [IHostIoCompletionManager:: Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="d2421-108">Notifies the CLR of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2421-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d2421-109">Remarks</span></span>  
 <span data-ttu-id="d2421-110">Der Host implementiert die e/a-Abschluss-Abstraktion mithilfe der [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d2421-110">The host implements the I/O completion abstraction by using the [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) interface.</span></span> <span data-ttu-id="d2421-111">Die CLR stellt e/a-Anforderungen über diese Schnittstelle und den Host benachrichtigt die Laufzeit über das Ergebnis des solche Anforderungen mithilfe der `ICLRIoCompletionManager` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d2421-111">The CLR makes I/O requests through this interface, and the host notifies the runtime of the outcome of such requests by using the `ICLRIoCompletionManager` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2421-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d2421-112">Requirements</span></span>  
 <span data-ttu-id="d2421-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2421-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2421-114">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d2421-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d2421-115">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d2421-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d2421-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2421-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2421-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2421-117">See Also</span></span>  
 [<span data-ttu-id="d2421-118">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d2421-118">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 [<span data-ttu-id="d2421-119">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d2421-119">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
 [<span data-ttu-id="d2421-120">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d2421-120">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
