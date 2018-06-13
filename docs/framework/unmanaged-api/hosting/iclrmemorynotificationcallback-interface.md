---
title: ICLRMemoryNotificationCallback-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMemoryNotificationCallback
helpviewer_keywords:
- ICLRMemoryNotificationCallback interface [.NET Framework hosting]
ms.assetid: 873639e2-4837-4568-83b3-4493e67e4174
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c5cf7e17989f3c083c7c4e52fa8cfc09c00bc7d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431518"
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="50607-102">ICLRMemoryNotificationCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="50607-102">ICLRMemoryNotificationCallback Interface</span></span>
<span data-ttu-id="50607-103">Der Host kann mit einem Ansatz ähnelt der des Win32-speicherauslastung des Berichts `CreateMemoryResourceNotification` Funktion.</span><span class="sxs-lookup"><span data-stu-id="50607-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="50607-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="50607-104">Methods</span></span>  
  
|<span data-ttu-id="50607-105">Methode</span><span class="sxs-lookup"><span data-stu-id="50607-105">Method</span></span>|<span data-ttu-id="50607-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="50607-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="50607-107">OnMemoryNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="50607-107">OnMemoryNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="50607-108">Benachrichtigt die common Language Runtime (CLR) von der Auslastung des Arbeitsspeichers auf dem Computer an.</span><span class="sxs-lookup"><span data-stu-id="50607-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50607-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="50607-109">Remarks</span></span>  
 <span data-ttu-id="50607-110">Vom Host verwendet die `ICLRMemoryNotificationCallback` Schnittstelle, um anzufordern, dass die CLR Geben Sie Arbeitsspeicherressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="50607-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50607-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="50607-111">Requirements</span></span>  
 <span data-ttu-id="50607-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50607-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50607-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="50607-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="50607-114">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="50607-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="50607-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50607-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50607-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50607-116">See Also</span></span>  
 [<span data-ttu-id="50607-117">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="50607-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="50607-118">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="50607-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
