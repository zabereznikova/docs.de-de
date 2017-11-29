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
ms.openlocfilehash: c378f2cd9b033e578ff15472a10a6dc295ad6539
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="b7ff7-102">EMemoryAvailable-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b7ff7-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="b7ff7-103">Enthält Werte, die die Menge des freien physischen Arbeitsspeichers auf dem Computer angeben.</span><span class="sxs-lookup"><span data-stu-id="b7ff7-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="b7ff7-104">Diese Werte logisch ordnen Sie auf die Ereignisse für die oberen und unteren zurückgegebene Arbeitsspeicher aus der `CreateMemoryResourceNotification` -Funktion in der Win32-API.</span><span class="sxs-lookup"><span data-stu-id="b7ff7-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Win32 API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7ff7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b7ff7-105">Syntax</span></span>  
  
```  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3   
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="b7ff7-106">Member</span><span class="sxs-lookup"><span data-stu-id="b7ff7-106">Members</span></span>  
  
|<span data-ttu-id="b7ff7-107">Member</span><span class="sxs-lookup"><span data-stu-id="b7ff7-107">Member</span></span>|<span data-ttu-id="b7ff7-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b7ff7-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="b7ff7-109">Viel physikalischer Speicher ist verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b7ff7-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="b7ff7-110">Sehr wenig physikalischer Speicher ist verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b7ff7-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="b7ff7-111">Der verfügbare physische Arbeitsspeicher ist neutral.</span><span class="sxs-lookup"><span data-stu-id="b7ff7-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7ff7-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b7ff7-112">Remarks</span></span>  
 <span data-ttu-id="b7ff7-113">Dieser Wert wird mithilfe eines Aufrufs vom Host zum die common Language Runtime (CLR) durch Übergeben der [ICLRMemoryNotificationCallback:: OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="b7ff7-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7ff7-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b7ff7-114">Requirements</span></span>  
 <span data-ttu-id="b7ff7-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7ff7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7ff7-116">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b7ff7-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b7ff7-117">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="b7ff7-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b7ff7-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7ff7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7ff7-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7ff7-119">See Also</span></span>  
 [<span data-ttu-id="b7ff7-120">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="b7ff7-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
