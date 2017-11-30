---
title: ICLRMemoryNotificationCallback-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMemoryNotificationCallback
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMemoryNotificationCallback
helpviewer_keywords: ICLRMemoryNotificationCallback interface [.NET Framework hosting]
ms.assetid: 873639e2-4837-4568-83b3-4493e67e4174
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6b998f8af2c7f4add3ecbb905928b5956409bf00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="e5b08-102">ICLRMemoryNotificationCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e5b08-102">ICLRMemoryNotificationCallback Interface</span></span>
<span data-ttu-id="e5b08-103">Der Host kann mit einem Ansatz ähnelt der des Win32-speicherauslastung des Berichts `CreateMemoryResourceNotification` Funktion.</span><span class="sxs-lookup"><span data-stu-id="e5b08-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e5b08-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="e5b08-104">Methods</span></span>  
  
|<span data-ttu-id="e5b08-105">Methode</span><span class="sxs-lookup"><span data-stu-id="e5b08-105">Method</span></span>|<span data-ttu-id="e5b08-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e5b08-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e5b08-107">OnMemoryNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="e5b08-107">OnMemoryNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="e5b08-108">Benachrichtigt die common Language Runtime (CLR) von der Auslastung des Arbeitsspeichers auf dem Computer an.</span><span class="sxs-lookup"><span data-stu-id="e5b08-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5b08-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e5b08-109">Remarks</span></span>  
 <span data-ttu-id="e5b08-110">Vom Host verwendet die `ICLRMemoryNotificationCallback` Schnittstelle, um anzufordern, dass die CLR Geben Sie Arbeitsspeicherressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="e5b08-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5b08-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e5b08-111">Requirements</span></span>  
 <span data-ttu-id="e5b08-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5b08-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5b08-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e5b08-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e5b08-114">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e5b08-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e5b08-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5b08-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5b08-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5b08-116">See Also</span></span>  
 [<span data-ttu-id="e5b08-117">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e5b08-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="e5b08-118">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e5b08-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
