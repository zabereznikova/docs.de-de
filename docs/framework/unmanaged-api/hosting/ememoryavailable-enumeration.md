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
ms.openlocfilehash: 6a8765bfd62a2e6543661804ab8d009ce19f8813
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724311"
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="cf73d-102">EMemoryAvailable-Enumeration</span><span class="sxs-lookup"><span data-stu-id="cf73d-102">EMemoryAvailable Enumeration</span></span>

<span data-ttu-id="cf73d-103">Enthält Werte, die angeben, wie viel freier physischer Speicher auf dem Computer vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="cf73d-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="cf73d-104">Diese Werte werden logisch den Ereignissen für den hoch-und Arbeitsspeicher zugeordnet, der von der- `CreateMemoryResourceNotification` Funktion in der Windows-API zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="cf73d-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Windows API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf73d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="cf73d-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="cf73d-106">Member</span><span class="sxs-lookup"><span data-stu-id="cf73d-106">Members</span></span>  
  
|<span data-ttu-id="cf73d-107">Member</span><span class="sxs-lookup"><span data-stu-id="cf73d-107">Member</span></span>|<span data-ttu-id="cf73d-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cf73d-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="cf73d-109">Es ist viel physischer Arbeitsspeicher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="cf73d-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="cf73d-110">Es ist nur wenig physischer Arbeitsspeicher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="cf73d-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="cf73d-111">Der verfügbare physische Speicher ist neutral.</span><span class="sxs-lookup"><span data-stu-id="cf73d-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf73d-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cf73d-112">Remarks</span></span>  

 <span data-ttu-id="cf73d-113">Dieser Wert wird vom Host mithilfe eines Aufrufs der [ICLRMemoryNotificationCallback:: OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md) -Methode an die Common Language Runtime (CLR) übergeben.</span><span class="sxs-lookup"><span data-stu-id="cf73d-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf73d-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="cf73d-114">Requirements</span></span>  

 <span data-ttu-id="cf73d-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf73d-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf73d-116">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="cf73d-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cf73d-117">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cf73d-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cf73d-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf73d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf73d-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cf73d-119">See also</span></span>

- [<span data-ttu-id="cf73d-120">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="cf73d-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
