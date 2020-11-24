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
ms.openlocfilehash: 5762a354bec485cb382b5460dfd2a337f79bee1a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689536"
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="ddf75-102">ICLRMemoryNotificationCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ddf75-102">ICLRMemoryNotificationCallback Interface</span></span>

<span data-ttu-id="ddf75-103">Ermöglicht es dem Host, Speicher Auslastungs Bedingungen mithilfe eines ähnlichen Ansatzes wie der Win32-Funktion zu melden `CreateMemoryResourceNotification` .</span><span class="sxs-lookup"><span data-stu-id="ddf75-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ddf75-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ddf75-104">Methods</span></span>  
  
|<span data-ttu-id="ddf75-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ddf75-105">Method</span></span>|<span data-ttu-id="ddf75-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ddf75-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ddf75-107">OnMemoryNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="ddf75-107">OnMemoryNotification Method</span></span>](iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="ddf75-108">Benachrichtigt den Common Language Runtime (CLR) über die Arbeitsspeicher Auslastung auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="ddf75-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ddf75-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ddf75-109">Remarks</span></span>  

 <span data-ttu-id="ddf75-110">Der Host verwendet die- `ICLRMemoryNotificationCallback` Schnittstelle, um anzufordern, dass die CLR Speicherressourcen freigibt.</span><span class="sxs-lookup"><span data-stu-id="ddf75-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddf75-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ddf75-111">Requirements</span></span>  

 <span data-ttu-id="ddf75-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ddf75-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddf75-113">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="ddf75-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ddf75-114">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ddf75-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ddf75-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddf75-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddf75-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ddf75-116">See also</span></span>

- [<span data-ttu-id="ddf75-117">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ddf75-117">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="ddf75-118">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ddf75-118">Hosting Interfaces</span></span>](hosting-interfaces.md)
