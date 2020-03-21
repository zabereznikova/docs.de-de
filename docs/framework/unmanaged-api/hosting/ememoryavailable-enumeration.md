---
title: EMemoryAvailable-Enumeration
ms.date: 03/30/2017
api_name:
- EMemoryAvailable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EMemoryAvailable
helpviewer_keywords:
- EMemoryAvailable enumeration [.NET Framework hosting]
ms.assetid: 38e72a06-dbed-473b-a59b-7e0b3ea4f2af
topic_type:
- apiref
ms.openlocfilehash: 0073a532f680d8764ec9e76ea22326a630457043
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176434"
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="55c12-102">EMemoryAvailable-Enumeration</span><span class="sxs-lookup"><span data-stu-id="55c12-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="55c12-103">Enthält Werte, die die Menge an freiem physischen Speicher auf dem Computer angeben.</span><span class="sxs-lookup"><span data-stu-id="55c12-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="55c12-104">Diese Werte werden logisch den Ereignissen für hohen `CreateMemoryResourceNotification` und niedrigen Speicher zugeordnet, die von der Funktion in der Windows-API zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="55c12-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Windows API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55c12-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="55c12-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="55c12-106">Members</span><span class="sxs-lookup"><span data-stu-id="55c12-106">Members</span></span>  
  
|<span data-ttu-id="55c12-107">Member</span><span class="sxs-lookup"><span data-stu-id="55c12-107">Member</span></span>|<span data-ttu-id="55c12-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="55c12-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="55c12-109">Es ist viel physischer Speicher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="55c12-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="55c12-110">Es ist nur sehr wenig physischer Speicher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="55c12-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="55c12-111">Der verfügbare physische Speicher ist neutral.</span><span class="sxs-lookup"><span data-stu-id="55c12-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55c12-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="55c12-112">Remarks</span></span>  
 <span data-ttu-id="55c12-113">Dieser Wert wird vom Host an die Common Language Runtime (CLR) übergeben, indem ein Aufruf der [ICLRMemoryNotificationCallback::OnMemoryNotification-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="55c12-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55c12-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="55c12-114">Requirements</span></span>  
 <span data-ttu-id="55c12-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55c12-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55c12-116">**Kopfzeile:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="55c12-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="55c12-117">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="55c12-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="55c12-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55c12-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55c12-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="55c12-119">See also</span></span>

- [<span data-ttu-id="55c12-120">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="55c12-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
