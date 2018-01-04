---
title: EMemoryAvailable-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EMemoryAvailable
api_location: mscoree.dll
api_type: COM
f1_keywords: EMemoryAvailable
helpviewer_keywords: EMemoryAvailable enumeration [.NET Framework hosting]
ms.assetid: 38e72a06-dbed-473b-a59b-7e0b3ea4f2af
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 596b174fa4ebac7e54e2f6b5f3ed044686fa515f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="e5a06-102">EMemoryAvailable-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e5a06-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="e5a06-103">Enthält Werte, die die Menge des freien physischen Arbeitsspeichers auf dem Computer angeben.</span><span class="sxs-lookup"><span data-stu-id="e5a06-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="e5a06-104">Diese Werte logisch ordnen Sie auf die Ereignisse für die oberen und unteren zurückgegebene Arbeitsspeicher aus der `CreateMemoryResourceNotification` -Funktion in der Win32-API.</span><span class="sxs-lookup"><span data-stu-id="e5a06-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Win32 API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5a06-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e5a06-105">Syntax</span></span>  
  
```  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3   
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="e5a06-106">Member</span><span class="sxs-lookup"><span data-stu-id="e5a06-106">Members</span></span>  
  
|<span data-ttu-id="e5a06-107">Member</span><span class="sxs-lookup"><span data-stu-id="e5a06-107">Member</span></span>|<span data-ttu-id="e5a06-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e5a06-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="e5a06-109">Viel physikalischer Speicher ist verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e5a06-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="e5a06-110">Sehr wenig physikalischer Speicher ist verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e5a06-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="e5a06-111">Der verfügbare physische Arbeitsspeicher ist neutral.</span><span class="sxs-lookup"><span data-stu-id="e5a06-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5a06-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e5a06-112">Remarks</span></span>  
 <span data-ttu-id="e5a06-113">Dieser Wert wird mithilfe eines Aufrufs vom Host zum die common Language Runtime (CLR) durch Übergeben der [ICLRMemoryNotificationCallback:: OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="e5a06-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5a06-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e5a06-114">Requirements</span></span>  
 <span data-ttu-id="e5a06-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5a06-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5a06-116">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e5a06-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e5a06-117">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="e5a06-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e5a06-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5a06-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5a06-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5a06-119">See Also</span></span>  
 [<span data-ttu-id="e5a06-120">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="e5a06-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
