---
title: WAIT_OPTION-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 143c191592efe8cfea8049f0dd5dc05a5bd4192f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="waitoption-enumeration"></a><span data-ttu-id="33347-102">WAIT_OPTION-Enumeration</span><span class="sxs-lookup"><span data-stu-id="33347-102">WAIT_OPTION Enumeration</span></span>
<span data-ttu-id="33347-103">Enthält Werte, die darauf, dass die Aktion eines Hosts durchführen soll, wenn ein Vorgang hinweisen, durch die common Language Runtime (CLR) Textblöcke angefordert.</span><span class="sxs-lookup"><span data-stu-id="33347-103">Contains values that indicate the action a host should take if an operation requested by the common language runtime (CLR) blocks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33347-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="33347-104">Syntax</span></span>  
  
```  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a><span data-ttu-id="33347-105">Member</span><span class="sxs-lookup"><span data-stu-id="33347-105">Members</span></span>  
  
|<span data-ttu-id="33347-106">Member</span><span class="sxs-lookup"><span data-stu-id="33347-106">Member</span></span>|<span data-ttu-id="33347-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="33347-107">Description</span></span>|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|<span data-ttu-id="33347-108">Benachrichtigt den Host, dass die Aufgabe aktiviert werden soll, wenn die CLR ruft die [IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="33347-108">Notifies the host that the task should be awakened if the CLR calls the [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) method.</span></span>|  
|`WAIT_MSGPUMP`|<span data-ttu-id="33347-109">Benachrichtigt den Host an, dass Nachrichten auf dem aktuellen Betriebssystemthread verteilt werden müssen, wenn der Thread blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="33347-109">Notifies the host that it must pump messages on the current OS thread if the thread becomes blocked.</span></span> <span data-ttu-id="33347-110">Die Common Language Runtime gibt diesen Wert nur auf eine <xref:System.Threading.ApartmentState.STA> Thread.</span><span class="sxs-lookup"><span data-stu-id="33347-110">The runtime specifies this value only on an <xref:System.Threading.ApartmentState.STA> thread.</span></span>|  
|`WAIT_NOTINDEADLOCK`|<span data-ttu-id="33347-111">Benachrichtigt den Host, dass die angegebenen synchronisierungsanforderung von einem Host aufgeteilt werden kann.</span><span class="sxs-lookup"><span data-stu-id="33347-111">Notifies the host that the specified synchronization request cannot be broken by a host.</span></span> <span data-ttu-id="33347-112">Der Host kann nicht zurückkehren, d. h. `HOST_E_DEADLOCK`.</span><span class="sxs-lookup"><span data-stu-id="33347-112">That is, the host cannot return `HOST_E_DEADLOCK`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33347-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="33347-113">Remarks</span></span>  
 <span data-ttu-id="33347-114">Die [IHostTaskManager:: Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) und [IHostTaskManager:: SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) beide Methoden akzeptieren einen Parameter dieses Typs.</span><span class="sxs-lookup"><span data-stu-id="33347-114">The [IHostTaskManager::Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) and [IHostTaskManager::SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) methods both take a parameter of this type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33347-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="33347-115">Requirements</span></span>  
 <span data-ttu-id="33347-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33347-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33347-117">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="33347-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="33347-118">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="33347-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="33347-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33347-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33347-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33347-120">See Also</span></span>  
 [<span data-ttu-id="33347-121">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="33347-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
