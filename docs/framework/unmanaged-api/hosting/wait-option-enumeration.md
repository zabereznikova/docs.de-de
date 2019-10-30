---
title: WAIT_OPTION-Enumeration
ms.date: 03/30/2017
api_name:
- WAIT_OPTION
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAIT_OPTION
helpviewer_keywords:
- WAIT_OPTION enumeration [.NET Framework hosting]
ms.assetid: 962fc293-8ded-4b3b-90ce-2c21a4f1b244
topic_type:
- apiref
ms.openlocfilehash: 9ecfb551b55551e5f6cc7e7e9ffb55e5a96259ee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141514"
---
# <a name="wait_option-enumeration"></a><span data-ttu-id="521c5-102">WAIT_OPTION-Enumeration</span><span class="sxs-lookup"><span data-stu-id="521c5-102">WAIT_OPTION Enumeration</span></span>
<span data-ttu-id="521c5-103">Enthält Werte, die angeben, welche Aktion ein Host durchführen soll, wenn ein vom Common Language Runtime (CLR)-Block angeforderter Vorgang ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="521c5-103">Contains values that indicate the action a host should take if an operation requested by the common language runtime (CLR) blocks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="521c5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="521c5-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a><span data-ttu-id="521c5-105">Member</span><span class="sxs-lookup"><span data-stu-id="521c5-105">Members</span></span>  
  
|<span data-ttu-id="521c5-106">Member</span><span class="sxs-lookup"><span data-stu-id="521c5-106">Member</span></span>|<span data-ttu-id="521c5-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="521c5-107">Description</span></span>|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|<span data-ttu-id="521c5-108">Benachrichtigt den Host, dass die Aufgabe ausgelöst werden soll, wenn die CLR die [IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) -Methode aufruft.</span><span class="sxs-lookup"><span data-stu-id="521c5-108">Notifies the host that the task should be awakened if the CLR calls the [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) method.</span></span>|  
|`WAIT_MSGPUMP`|<span data-ttu-id="521c5-109">Benachrichtigt den Host, dass er Nachrichten auf dem aktuellen Betriebssystem Thread verschieben muss, wenn der Thread blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="521c5-109">Notifies the host that it must pump messages on the current OS thread if the thread becomes blocked.</span></span> <span data-ttu-id="521c5-110">Die Laufzeit gibt diesen Wert nur in einem <xref:System.Threading.ApartmentState.STA> Thread an.</span><span class="sxs-lookup"><span data-stu-id="521c5-110">The runtime specifies this value only on an <xref:System.Threading.ApartmentState.STA> thread.</span></span>|  
|`WAIT_NOTINDEADLOCK`|<span data-ttu-id="521c5-111">Benachrichtigt den Host, dass die angegebene Synchronisierungs Anforderung nicht von einem Host getrennt werden kann.</span><span class="sxs-lookup"><span data-stu-id="521c5-111">Notifies the host that the specified synchronization request cannot be broken by a host.</span></span> <span data-ttu-id="521c5-112">Das heißt, der Host kann keine `HOST_E_DEADLOCK`zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="521c5-112">That is, the host cannot return `HOST_E_DEADLOCK`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="521c5-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="521c5-113">Remarks</span></span>  
 <span data-ttu-id="521c5-114">Die [IHostTaskManager:: Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) -und [IHostTaskManager:: switchdetask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) -Methoden akzeptieren beide einen Parameter dieses Typs.</span><span class="sxs-lookup"><span data-stu-id="521c5-114">The [IHostTaskManager::Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) and [IHostTaskManager::SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) methods both take a parameter of this type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="521c5-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="521c5-115">Requirements</span></span>  
 <span data-ttu-id="521c5-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="521c5-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="521c5-117">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="521c5-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="521c5-118">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="521c5-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="521c5-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="521c5-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="521c5-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="521c5-120">See also</span></span>

- [<span data-ttu-id="521c5-121">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="521c5-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
