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
ms.openlocfilehash: e980356ad592e137df7d08dadd77431b0e295380
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141002"
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="e0d58-102">ICLRMemoryNotificationCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e0d58-102">ICLRMemoryNotificationCallback Interface</span></span>
<span data-ttu-id="e0d58-103">Ermöglicht es dem Host, Speicher Auslastungs Bedingungen mithilfe eines ähnlichen Ansatzes wie der Win32-`CreateMemoryResourceNotification` Funktion zu melden.</span><span class="sxs-lookup"><span data-stu-id="e0d58-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e0d58-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="e0d58-104">Methods</span></span>  
  
|<span data-ttu-id="e0d58-105">Methode</span><span class="sxs-lookup"><span data-stu-id="e0d58-105">Method</span></span>|<span data-ttu-id="e0d58-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0d58-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e0d58-107">OnMemoryNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="e0d58-107">OnMemoryNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="e0d58-108">Benachrichtigt den Common Language Runtime (CLR) über die Arbeitsspeicher Auslastung auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="e0d58-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0d58-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e0d58-109">Remarks</span></span>  
 <span data-ttu-id="e0d58-110">Der Host verwendet die `ICLRMemoryNotificationCallback`-Schnittstelle, um anzufordern, dass die CLR Speicherressourcen freigibt.</span><span class="sxs-lookup"><span data-stu-id="e0d58-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0d58-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e0d58-111">Requirements</span></span>  
 <span data-ttu-id="e0d58-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0d58-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0d58-113">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="e0d58-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e0d58-114">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e0d58-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e0d58-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0d58-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0d58-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0d58-116">See also</span></span>

- [<span data-ttu-id="e0d58-117">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e0d58-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="e0d58-118">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e0d58-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
