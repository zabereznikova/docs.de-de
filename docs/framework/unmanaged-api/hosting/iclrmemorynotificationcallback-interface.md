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
ms.workload: dotnet
ms.openlocfilehash: cc09e3668dc814360de0256c2476ffa7b61462ed
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="de7cf-102">ICLRMemoryNotificationCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="de7cf-102">ICLRMemoryNotificationCallback Interface</span></span>
<span data-ttu-id="de7cf-103">Der Host kann mit einem Ansatz ähnelt der des Win32-speicherauslastung des Berichts `CreateMemoryResourceNotification` Funktion.</span><span class="sxs-lookup"><span data-stu-id="de7cf-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="de7cf-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="de7cf-104">Methods</span></span>  
  
|<span data-ttu-id="de7cf-105">Methode</span><span class="sxs-lookup"><span data-stu-id="de7cf-105">Method</span></span>|<span data-ttu-id="de7cf-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="de7cf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="de7cf-107">OnMemoryNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="de7cf-107">OnMemoryNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="de7cf-108">Benachrichtigt die common Language Runtime (CLR) von der Auslastung des Arbeitsspeichers auf dem Computer an.</span><span class="sxs-lookup"><span data-stu-id="de7cf-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de7cf-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="de7cf-109">Remarks</span></span>  
 <span data-ttu-id="de7cf-110">Vom Host verwendet die `ICLRMemoryNotificationCallback` Schnittstelle, um anzufordern, dass die CLR Geben Sie Arbeitsspeicherressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="de7cf-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de7cf-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="de7cf-111">Requirements</span></span>  
 <span data-ttu-id="de7cf-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de7cf-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de7cf-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="de7cf-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="de7cf-114">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="de7cf-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="de7cf-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de7cf-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de7cf-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de7cf-116">See Also</span></span>  
 [<span data-ttu-id="de7cf-117">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="de7cf-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="de7cf-118">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="de7cf-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
