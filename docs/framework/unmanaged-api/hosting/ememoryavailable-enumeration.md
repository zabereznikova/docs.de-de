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
ms.openlocfilehash: 822396e28d000a5309738680fec502e1aeacd67c
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616215"
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="5bd92-102">EMemoryAvailable-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5bd92-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="5bd92-103">Enthält Werte, die angeben, wie viel freier physischer Speicher auf dem Computer vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="5bd92-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="5bd92-104">Diese Werte werden logisch den Ereignissen für den hoch-und Arbeitsspeicher zugeordnet, der von der- `CreateMemoryResourceNotification` Funktion in der Windows-API zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5bd92-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Windows API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bd92-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5bd92-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="5bd92-106">Member</span><span class="sxs-lookup"><span data-stu-id="5bd92-106">Members</span></span>  
  
|<span data-ttu-id="5bd92-107">Member</span><span class="sxs-lookup"><span data-stu-id="5bd92-107">Member</span></span>|<span data-ttu-id="5bd92-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5bd92-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="5bd92-109">Es ist viel physischer Arbeitsspeicher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5bd92-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="5bd92-110">Es ist nur wenig physischer Arbeitsspeicher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5bd92-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="5bd92-111">Der verfügbare physische Speicher ist neutral.</span><span class="sxs-lookup"><span data-stu-id="5bd92-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5bd92-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5bd92-112">Remarks</span></span>  
 <span data-ttu-id="5bd92-113">Dieser Wert wird vom Host mithilfe eines Aufrufs der [ICLRMemoryNotificationCallback:: OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md) -Methode an die Common Language Runtime (CLR) übergeben.</span><span class="sxs-lookup"><span data-stu-id="5bd92-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bd92-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5bd92-114">Requirements</span></span>  
 <span data-ttu-id="5bd92-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5bd92-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bd92-116">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="5bd92-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5bd92-117">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="5bd92-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5bd92-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bd92-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bd92-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5bd92-119">See also</span></span>

- [<span data-ttu-id="5bd92-120">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="5bd92-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
