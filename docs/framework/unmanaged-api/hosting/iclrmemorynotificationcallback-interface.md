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
ms.openlocfilehash: b3167d288a57575af85a9cb50f5c0cd82c8e9cc9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54702794"
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="92cf1-102">ICLRMemoryNotificationCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="92cf1-102">ICLRMemoryNotificationCallback Interface</span></span>
<span data-ttu-id="92cf1-103">Ermöglicht dem Host, den Berichts-speicherauslastung, die mit einem Ansatz ähnelt der von der Win32 `CreateMemoryResourceNotification` Funktion.</span><span class="sxs-lookup"><span data-stu-id="92cf1-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="92cf1-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="92cf1-104">Methods</span></span>  
  
|<span data-ttu-id="92cf1-105">Methode</span><span class="sxs-lookup"><span data-stu-id="92cf1-105">Method</span></span>|<span data-ttu-id="92cf1-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="92cf1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="92cf1-107">OnMemoryNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="92cf1-107">OnMemoryNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="92cf1-108">Benachrichtigt die common Language Runtime (CLR) von der Auslastung des Arbeitsspeichers auf dem Computer an.</span><span class="sxs-lookup"><span data-stu-id="92cf1-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92cf1-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="92cf1-109">Remarks</span></span>  
 <span data-ttu-id="92cf1-110">Der Host verwendet die `ICLRMemoryNotificationCallback` Schnittstelle anfordern, dass die CLR Geben Sie Arbeitsspeicherressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="92cf1-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92cf1-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="92cf1-111">Requirements</span></span>  
 <span data-ttu-id="92cf1-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92cf1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92cf1-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="92cf1-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="92cf1-114">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="92cf1-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="92cf1-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92cf1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92cf1-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92cf1-116">See also</span></span>
- [<span data-ttu-id="92cf1-117">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="92cf1-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="92cf1-118">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="92cf1-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
