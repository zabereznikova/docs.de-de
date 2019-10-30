---
title: EClrEvent-Enumeration
ms.date: 03/30/2017
api_name:
- EClrEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrEvent
helpviewer_keywords:
- EClrEvent enumeration [.NET Framework hosting]
ms.assetid: 7c36a7c2-75a2-4971-bc23-abf54c812154
topic_type:
- apiref
ms.openlocfilehash: ee749fd40f440e92f1d1b09c2ea5e7bdd51f1cbe
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131133"
---
# <a name="eclrevent-enumeration"></a><span data-ttu-id="84d2c-102">EClrEvent-Enumeration</span><span class="sxs-lookup"><span data-stu-id="84d2c-102">EClrEvent Enumeration</span></span>
<span data-ttu-id="84d2c-103">Beschreibt die Common Language Runtime (CLR)-Ereignisse, für die der Host Rückrufe registrieren kann.</span><span class="sxs-lookup"><span data-stu-id="84d2c-103">Describes the common language runtime (CLR) events for which the host can register callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84d2c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="84d2c-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    Event_ClrDisabled,  
    Event_DomainUnload,  
    Event_MDAFired,  
    Event_StackOverflow  
} EClrEvent;  
```  
  
## <a name="members"></a><span data-ttu-id="84d2c-105">Member</span><span class="sxs-lookup"><span data-stu-id="84d2c-105">Members</span></span>  
  
|<span data-ttu-id="84d2c-106">Member</span><span class="sxs-lookup"><span data-stu-id="84d2c-106">Member</span></span>|<span data-ttu-id="84d2c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="84d2c-107">Description</span></span>|  
|------------|-----------------|  
|`Event_ClrDisabled`|<span data-ttu-id="84d2c-108">Gibt einen schwerwiegenden CLR-Fehler an.</span><span class="sxs-lookup"><span data-stu-id="84d2c-108">Specifies a fatal CLR error.</span></span>|  
|`Event_DomainUnload`|<span data-ttu-id="84d2c-109">Gibt das Entladen eines bestimmten <xref:System.AppDomain>an.</span><span class="sxs-lookup"><span data-stu-id="84d2c-109">Specifies the unloading of a particular <xref:System.AppDomain>.</span></span>|  
|`Event_MDAFired`|<span data-ttu-id="84d2c-110">Gibt an, dass eine MDA-Nachricht (Managed Debug Assistant) generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="84d2c-110">Specifies that a Managed Debugging Assistant (MDA) message has been generated.</span></span>|  
|`Event_StackOverflow`|<span data-ttu-id="84d2c-111">Gibt an, dass ein Stapelüberlauf Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="84d2c-111">Specifies that a stack overflow error has occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84d2c-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="84d2c-112">Remarks</span></span>  
 <span data-ttu-id="84d2c-113">Der Host kann Rückrufe für jeden der Ereignis Typen registrieren, die von `EClrEvent` beschrieben werden, indem Methoden der [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) -Schnittstelle aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="84d2c-113">The host can register callbacks for any of the event types described by `EClrEvent` by calling methods of the [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) interface.</span></span> <span data-ttu-id="84d2c-114">Der Host erhält einen Zeiger auf diese Schnittstelle, indem er die [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) -Methode aufruft.</span><span class="sxs-lookup"><span data-stu-id="84d2c-114">The host gets a pointer to this interface by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
 <span data-ttu-id="84d2c-115">Die `Event_CLRDisabled`-und `Event_DomainUnload` Ereignisse können mehrmals und aus unterschiedlichen Threads ausgelöst werden, um eine Entladung oder die Deaktivierung der CLR zu signalisieren.</span><span class="sxs-lookup"><span data-stu-id="84d2c-115">The `Event_CLRDisabled` and `Event_DomainUnload` events can be raised more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
 <span data-ttu-id="84d2c-116">Das `Event_MDAFired`-Ereignis löst die Erstellung einer [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) -Instanz aus, die die Details der MDA-Nachricht enthält.</span><span class="sxs-lookup"><span data-stu-id="84d2c-116">The `Event_MDAFired` event raises the creation of an [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) instance that contains the details of the MDA message.</span></span> <span data-ttu-id="84d2c-117">Weitere Informationen zu MDAs finden Sie unter [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="84d2c-117">For more information about MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84d2c-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="84d2c-118">Requirements</span></span>  
 <span data-ttu-id="84d2c-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84d2c-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84d2c-120">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="84d2c-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="84d2c-121">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="84d2c-121">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84d2c-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84d2c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84d2c-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84d2c-123">See also</span></span>

- [<span data-ttu-id="84d2c-124">IActionOnCLREvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84d2c-124">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="84d2c-125">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84d2c-125">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="84d2c-126">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="84d2c-126">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
