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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 55463985a7ac93bf0ec3cda92f91f8a326f92406
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410562"
---
# <a name="ememoryavailable-enumeration"></a><span data-ttu-id="9833c-102">EMemoryAvailable-Enumeration</span><span class="sxs-lookup"><span data-stu-id="9833c-102">EMemoryAvailable Enumeration</span></span>
<span data-ttu-id="9833c-103">Enthält Werte, die die Menge des freien physischen Arbeitsspeichers auf dem Computer angeben.</span><span class="sxs-lookup"><span data-stu-id="9833c-103">Contains values that indicate the amount of free physical memory on the computer.</span></span> <span data-ttu-id="9833c-104">Diese Werte logisch sind die Ereignisse für die oberen und unteren zurückgegebene Arbeitsspeicher aus dem `CreateMemoryResourceNotification` -Funktion in der Windows-API.</span><span class="sxs-lookup"><span data-stu-id="9833c-104">These values logically map to the events for high and low memory returned from the `CreateMemoryResourceNotification` function in the Windows API.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9833c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9833c-105">Syntax</span></span>  
  
```  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3   
} EMemoryAvailable;  
```  
  
## <a name="members"></a><span data-ttu-id="9833c-106">Member</span><span class="sxs-lookup"><span data-stu-id="9833c-106">Members</span></span>  
  
|<span data-ttu-id="9833c-107">Member</span><span class="sxs-lookup"><span data-stu-id="9833c-107">Member</span></span>|<span data-ttu-id="9833c-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9833c-108">Description</span></span>|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|<span data-ttu-id="9833c-109">Viel physikalischer Speicher ist verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9833c-109">Plenty of physical memory is available.</span></span>|  
|`eMemoryAvailableLow`|<span data-ttu-id="9833c-110">Es ist nur wenig physischer Speicher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9833c-110">Very little physical memory is available.</span></span>|  
|`eMemoryAvailableNeutral`|<span data-ttu-id="9833c-111">Der verfügbare physische Arbeitsspeicher ist neutral.</span><span class="sxs-lookup"><span data-stu-id="9833c-111">The available physical memory is neutral.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9833c-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9833c-112">Remarks</span></span>  
 <span data-ttu-id="9833c-113">Dieser Wert wird mithilfe eines Aufrufs vom Host die common Language Runtime (CLR) durch Übergeben der [ICLRMemoryNotificationCallback:: OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="9833c-113">This value is passed by the host to the common language runtime (CLR) by using a call to the [ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9833c-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9833c-114">Requirements</span></span>  
 <span data-ttu-id="9833c-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9833c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9833c-116">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9833c-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9833c-117">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9833c-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9833c-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9833c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9833c-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9833c-119">See also</span></span>
- [<span data-ttu-id="9833c-120">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="9833c-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
