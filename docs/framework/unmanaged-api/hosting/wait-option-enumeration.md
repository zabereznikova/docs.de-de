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
ms.openlocfilehash: 056d41df328de5796eec9f04589205d18b408f1f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732800"
---
# <a name="wait_option-enumeration"></a><span data-ttu-id="c7785-102">WAIT_OPTION-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c7785-102">WAIT_OPTION Enumeration</span></span>

<span data-ttu-id="c7785-103">Enthält Werte, die angeben, welche Aktion ein Host durchführen soll, wenn ein vom Common Language Runtime (CLR)-Block angeforderter Vorgang ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c7785-103">Contains values that indicate the action a host should take if an operation requested by the common language runtime (CLR) blocks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7785-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c7785-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a><span data-ttu-id="c7785-105">Member</span><span class="sxs-lookup"><span data-stu-id="c7785-105">Members</span></span>  
  
|<span data-ttu-id="c7785-106">Member</span><span class="sxs-lookup"><span data-stu-id="c7785-106">Member</span></span>|<span data-ttu-id="c7785-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c7785-107">Description</span></span>|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|<span data-ttu-id="c7785-108">Benachrichtigt den Host, dass die Aufgabe ausgelöst werden soll, wenn die CLR die [IHostTask:: Alert](ihosttask-alert-method.md) -Methode aufruft.</span><span class="sxs-lookup"><span data-stu-id="c7785-108">Notifies the host that the task should be awakened if the CLR calls the [IHostTask::Alert](ihosttask-alert-method.md) method.</span></span>|  
|`WAIT_MSGPUMP`|<span data-ttu-id="c7785-109">Benachrichtigt den Host, dass er Nachrichten auf dem aktuellen Betriebssystem Thread verschieben muss, wenn der Thread blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="c7785-109">Notifies the host that it must pump messages on the current OS thread if the thread becomes blocked.</span></span> <span data-ttu-id="c7785-110">Die Laufzeit gibt diesen Wert nur in einem <xref:System.Threading.ApartmentState.STA> Thread an.</span><span class="sxs-lookup"><span data-stu-id="c7785-110">The runtime specifies this value only on an <xref:System.Threading.ApartmentState.STA> thread.</span></span>|  
|`WAIT_NOTINDEADLOCK`|<span data-ttu-id="c7785-111">Benachrichtigt den Host, dass die angegebene Synchronisierungs Anforderung nicht von einem Host getrennt werden kann.</span><span class="sxs-lookup"><span data-stu-id="c7785-111">Notifies the host that the specified synchronization request cannot be broken by a host.</span></span> <span data-ttu-id="c7785-112">Das heißt, der Host kann nicht zurückgeben `HOST_E_DEADLOCK` .</span><span class="sxs-lookup"><span data-stu-id="c7785-112">That is, the host cannot return `HOST_E_DEADLOCK`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7785-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c7785-113">Remarks</span></span>  

 <span data-ttu-id="c7785-114">Die [IHostTaskManager:: Sleep](ihosttaskmanager-sleep-method.md) -und [IHostTaskManager:: switchdetask](ihosttaskmanager-switchtotask-method.md) -Methoden akzeptieren beide einen Parameter dieses Typs.</span><span class="sxs-lookup"><span data-stu-id="c7785-114">The [IHostTaskManager::Sleep](ihosttaskmanager-sleep-method.md) and [IHostTaskManager::SwitchToTask](ihosttaskmanager-switchtotask-method.md) methods both take a parameter of this type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7785-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c7785-115">Requirements</span></span>  

 <span data-ttu-id="c7785-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7785-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7785-117">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="c7785-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c7785-118">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c7785-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c7785-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7785-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7785-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c7785-120">See also</span></span>

- [<span data-ttu-id="c7785-121">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="c7785-121">Hosting Enumerations</span></span>](hosting-enumerations.md)
