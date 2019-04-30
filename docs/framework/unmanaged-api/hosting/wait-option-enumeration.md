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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ac28f28d4d284ba26fadd46e53ebeb8e5b5f3cd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61984151"
---
# <a name="waitoption-enumeration"></a><span data-ttu-id="cb390-102">WAIT_OPTION-Enumeration</span><span class="sxs-lookup"><span data-stu-id="cb390-102">WAIT_OPTION Enumeration</span></span>
<span data-ttu-id="cb390-103">Enthält Werte, die angeben, dass die Aktion eines Hosts durchführen soll, wenn ein Vorgang angefordert wird, durch die common Language Runtime (CLR) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cb390-103">Contains values that indicate the action a host should take if an operation requested by the common language runtime (CLR) blocks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb390-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cb390-104">Syntax</span></span>  
  
```  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a><span data-ttu-id="cb390-105">Member</span><span class="sxs-lookup"><span data-stu-id="cb390-105">Members</span></span>  
  
|<span data-ttu-id="cb390-106">Member</span><span class="sxs-lookup"><span data-stu-id="cb390-106">Member</span></span>|<span data-ttu-id="cb390-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cb390-107">Description</span></span>|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|<span data-ttu-id="cb390-108">Benachrichtigt den Host, dass die Aufgabe aktiviert werden soll, wenn die CLR ruft die [IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="cb390-108">Notifies the host that the task should be awakened if the CLR calls the [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) method.</span></span>|  
|`WAIT_MSGPUMP`|<span data-ttu-id="cb390-109">Benachrichtigt den Host an, dass Nachrichten in der aktuellen BS-Thread verteilt werden müssen, wenn der Thread blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="cb390-109">Notifies the host that it must pump messages on the current OS thread if the thread becomes blocked.</span></span> <span data-ttu-id="cb390-110">Die Common Language Runtime gibt dieser Wert nur auf eine <xref:System.Threading.ApartmentState.STA> Thread.</span><span class="sxs-lookup"><span data-stu-id="cb390-110">The runtime specifies this value only on an <xref:System.Threading.ApartmentState.STA> thread.</span></span>|  
|`WAIT_NOTINDEADLOCK`|<span data-ttu-id="cb390-111">Benachrichtigt den Host, dass die angegebene synchronisierungsanforderung von einem Host aufgeteilt werden kann.</span><span class="sxs-lookup"><span data-stu-id="cb390-111">Notifies the host that the specified synchronization request cannot be broken by a host.</span></span> <span data-ttu-id="cb390-112">Der Host kann nicht zurückkehren, d. h. `HOST_E_DEADLOCK`.</span><span class="sxs-lookup"><span data-stu-id="cb390-112">That is, the host cannot return `HOST_E_DEADLOCK`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb390-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cb390-113">Remarks</span></span>  
 <span data-ttu-id="cb390-114">Die [IHostTaskManager:: Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) und [IHostTaskManager:: SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) beide Methoden akzeptieren einen Parameter dieses Typs.</span><span class="sxs-lookup"><span data-stu-id="cb390-114">The [IHostTaskManager::Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) and [IHostTaskManager::SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) methods both take a parameter of this type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb390-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cb390-115">Requirements</span></span>  
 <span data-ttu-id="cb390-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb390-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb390-117">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cb390-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cb390-118">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cb390-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cb390-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb390-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb390-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb390-120">See also</span></span>

- [<span data-ttu-id="cb390-121">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="cb390-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
