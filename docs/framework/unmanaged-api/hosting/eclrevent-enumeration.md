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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13d564be68d6b49a1616be97710312f33f828d48
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59176344"
---
# <a name="eclrevent-enumeration"></a><span data-ttu-id="2129e-102">EClrEvent-Enumeration</span><span class="sxs-lookup"><span data-stu-id="2129e-102">EClrEvent Enumeration</span></span>
<span data-ttu-id="2129e-103">Beschreibt die common Language Runtime (CLR)-Ereignisse für die der Host Rückrufe registrieren kann.</span><span class="sxs-lookup"><span data-stu-id="2129e-103">Describes the common language runtime (CLR) events for which the host can register callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2129e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2129e-104">Syntax</span></span>  
  
```  
typedef enum {  
    Event_ClrDisabled,  
    Event_DomainUnload,  
    Event_MDAFired,  
    Event_StackOverflow  
} EClrEvent;  
```  
  
## <a name="members"></a><span data-ttu-id="2129e-105">Member</span><span class="sxs-lookup"><span data-stu-id="2129e-105">Members</span></span>  
  
|<span data-ttu-id="2129e-106">Member</span><span class="sxs-lookup"><span data-stu-id="2129e-106">Member</span></span>|<span data-ttu-id="2129e-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2129e-107">Description</span></span>|  
|------------|-----------------|  
|`Event_ClrDisabled`|<span data-ttu-id="2129e-108">Gibt einen schwerwiegenden Fehler für die CLR.</span><span class="sxs-lookup"><span data-stu-id="2129e-108">Specifies a fatal CLR error.</span></span>|  
|`Event_DomainUnload`|<span data-ttu-id="2129e-109">Gibt an, das Entladen eines bestimmten <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="2129e-109">Specifies the unloading of a particular <xref:System.AppDomain>.</span></span>|  
|`Event_MDAFired`|<span data-ttu-id="2129e-110">Gibt an, dass eine Nachricht des Assistenten für verwaltetes Debuggen (Managed Debugging Assistant, MDA) generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="2129e-110">Specifies that a Managed Debugging Assistant (MDA) message has been generated.</span></span>|  
|`Event_StackOverflow`|<span data-ttu-id="2129e-111">Gibt an, dass ein Stapelüberlauf auftritt, aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="2129e-111">Specifies that a stack overflow error has occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2129e-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2129e-112">Remarks</span></span>  
 <span data-ttu-id="2129e-113">Der Host kann Rückrufe für alle Ereignistypen, die durch beschrieben registrieren `EClrEvent` durch Aufrufen der Methoden, die von der [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="2129e-113">The host can register callbacks for any of the event types described by `EClrEvent` by calling methods of the [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) interface.</span></span> <span data-ttu-id="2129e-114">Der Host Ruft einen Zeiger auf diese Schnittstelle ab, durch den Aufruf der [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="2129e-114">The host gets a pointer to this interface by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
 <span data-ttu-id="2129e-115">Die `Event_CLRDisabled` und `Event_DomainUnload` Ereignisse ausgelöst werden können, mehr als einmal und von verschiedenen Threads ein Entladen oder das Deaktivieren der CLR signalisiert.</span><span class="sxs-lookup"><span data-stu-id="2129e-115">The `Event_CLRDisabled` and `Event_DomainUnload` events can be raised more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
 <span data-ttu-id="2129e-116">Die `Event_MDAFired` Ereignis löst die Erstellung einer [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) -Instanz, die die Details der MDA-Meldung enthält.</span><span class="sxs-lookup"><span data-stu-id="2129e-116">The `Event_MDAFired` event raises the creation of an [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) instance that contains the details of the MDA message.</span></span> <span data-ttu-id="2129e-117">Weitere Informationen über MDAs finden Sie unter [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="2129e-117">For more information about MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2129e-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2129e-118">Requirements</span></span>  
 <span data-ttu-id="2129e-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2129e-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2129e-120">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2129e-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2129e-121">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2129e-121">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="2129e-122">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="2129e-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2129e-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2129e-123">See also</span></span>

- [<span data-ttu-id="2129e-124">IActionOnCLREvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2129e-124">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="2129e-125">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2129e-125">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="2129e-126">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="2129e-126">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
