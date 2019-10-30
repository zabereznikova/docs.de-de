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
ms.openlocfilehash: aec3c5f140df7eab10ea2bfa33634a4d853adcb0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134291"
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="7223f-102">EMemoryAvailable-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7223f-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="7223f-103">Enthält Werte, die angeben, wie viel freier physischer Speicher auf dem Computer vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="7223f-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="7223f-104">Diese Werte werden logisch den Ereignissen für einen hohen und niedrigen Arbeitsspeicher zugeordnet, der von der `CreateMemoryResourceNotification` Funktion in der Windows-API zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7223f-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Windows API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7223f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7223f-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3   
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="7223f-106">Member</span><span class="sxs-lookup"><span data-stu-id="7223f-106">Members</span></span>  
  
|<span data-ttu-id="7223f-107">Member</span><span class="sxs-lookup"><span data-stu-id="7223f-107">Member</span></span>|<span data-ttu-id="7223f-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7223f-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="7223f-109">Es ist viel physischer Arbeitsspeicher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7223f-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="7223f-110">Es ist nur wenig physischer Arbeitsspeicher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7223f-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="7223f-111">Der verfügbare physische Speicher ist neutral.</span><span class="sxs-lookup"><span data-stu-id="7223f-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7223f-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7223f-112">Remarks</span></span>  
 <span data-ttu-id="7223f-113">Dieser Wert wird vom Host mithilfe eines Aufrufs der [ICLRMemoryNotificationCallback:: OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) -Methode an die Common Language Runtime (CLR) übergeben.</span><span class="sxs-lookup"><span data-stu-id="7223f-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7223f-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7223f-114">Requirements</span></span>  
 <span data-ttu-id="7223f-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7223f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7223f-116">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="7223f-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7223f-117">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="7223f-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7223f-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7223f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7223f-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7223f-119">See also</span></span>

- [<span data-ttu-id="7223f-120">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="7223f-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
