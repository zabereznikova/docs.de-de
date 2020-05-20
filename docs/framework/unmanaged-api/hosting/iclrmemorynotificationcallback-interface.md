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
ms.openlocfilehash: 52fc21044d345998ad72c045cdf5e80a8a03a38e
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703802"
---
# <a name="iclrmemorynotificationcallback-interface"></a><span data-ttu-id="51f4c-102">ICLRMemoryNotificationCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="51f4c-102">ICLRMemoryNotificationCallback Interface</span></span>
<span data-ttu-id="51f4c-103">Ermöglicht es dem Host, Speicher Auslastungs Bedingungen mithilfe eines ähnlichen Ansatzes wie der Win32-Funktion zu melden `CreateMemoryResourceNotification` .</span><span class="sxs-lookup"><span data-stu-id="51f4c-103">Allows the host to report memory pressure conditions using an approach similar to that of the Win32 `CreateMemoryResourceNotification` function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="51f4c-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="51f4c-104">Methods</span></span>  
  
|<span data-ttu-id="51f4c-105">Methode</span><span class="sxs-lookup"><span data-stu-id="51f4c-105">Method</span></span>|<span data-ttu-id="51f4c-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="51f4c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="51f4c-107">OnMemoryNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="51f4c-107">OnMemoryNotification Method</span></span>](iclrmemorynotificationcallback-onmemorynotification-method.md)|<span data-ttu-id="51f4c-108">Benachrichtigt den Common Language Runtime (CLR) über die Arbeitsspeicher Auslastung auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="51f4c-108">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51f4c-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="51f4c-109">Remarks</span></span>  
 <span data-ttu-id="51f4c-110">Der Host verwendet die- `ICLRMemoryNotificationCallback` Schnittstelle, um anzufordern, dass die CLR Speicherressourcen freigibt.</span><span class="sxs-lookup"><span data-stu-id="51f4c-110">The host uses the `ICLRMemoryNotificationCallback` interface to request that the CLR free memory resources.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51f4c-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="51f4c-111">Requirements</span></span>  
 <span data-ttu-id="51f4c-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51f4c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51f4c-113">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="51f4c-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="51f4c-114">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="51f4c-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="51f4c-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51f4c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51f4c-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51f4c-116">See also</span></span>

- [<span data-ttu-id="51f4c-117">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="51f4c-117">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="51f4c-118">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="51f4c-118">Hosting Interfaces</span></span>](hosting-interfaces.md)
