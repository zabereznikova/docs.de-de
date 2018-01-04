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
ms.workload: dotnet
ms.openlocfilehash: 99dc183674abaff33047f070c14794150a8615f0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclriocompletionmanager-interface"></a><span data-ttu-id="4e0b3-102">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4e0b3-102">ICLRIoCompletionManager Interface</span></span>
<span data-ttu-id="4e0b3-103">Implementiert fordert eine Rückrufmethode, die den Host zu benachrichtigen, die common Language Runtime (CLR) den Status der angegebenen e/a ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="4e0b3-103">Implements a callback method that allows the host to notify the common language runtime (CLR) of the status of specified I/O requests.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4e0b3-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="4e0b3-104">Methods</span></span>  
  
|<span data-ttu-id="4e0b3-105">Methode</span><span class="sxs-lookup"><span data-stu-id="4e0b3-105">Method</span></span>|<span data-ttu-id="4e0b3-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4e0b3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4e0b3-107">OnComplete-Methode</span><span class="sxs-lookup"><span data-stu-id="4e0b3-107">OnComplete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|<span data-ttu-id="4e0b3-108">Benachrichtigt die CLR über den Status einer e/a-Anforderung, die erstellt wurde, mithilfe eines Aufrufs an die [IHostIoCompletionManager:: Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="4e0b3-108">Notifies the CLR of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e0b3-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4e0b3-109">Remarks</span></span>  
 <span data-ttu-id="4e0b3-110">Der Host implementiert die e/a-Abschluss-Abstraktion mithilfe der [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="4e0b3-110">The host implements the I/O completion abstraction by using the [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) interface.</span></span> <span data-ttu-id="4e0b3-111">Die CLR stellt e/a-Anforderungen über diese Schnittstelle und den Host benachrichtigt die Laufzeit über das Ergebnis des solche Anforderungen mithilfe der `ICLRIoCompletionManager` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="4e0b3-111">The CLR makes I/O requests through this interface, and the host notifies the runtime of the outcome of such requests by using the `ICLRIoCompletionManager` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e0b3-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4e0b3-112">Requirements</span></span>  
 <span data-ttu-id="4e0b3-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e0b3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e0b3-114">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4e0b3-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4e0b3-115">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4e0b3-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4e0b3-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e0b3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e0b3-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e0b3-117">See Also</span></span>  
 [<span data-ttu-id="4e0b3-118">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4e0b3-118">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 [<span data-ttu-id="4e0b3-119">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4e0b3-119">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
 [<span data-ttu-id="4e0b3-120">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="4e0b3-120">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
