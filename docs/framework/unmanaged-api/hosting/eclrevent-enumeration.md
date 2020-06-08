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
ms.openlocfilehash: 3ecaebb9d943a3cdbb231307012b5dc3aaf000f7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493400"
---
# <a name="eclrevent-enumeration"></a><span data-ttu-id="09e53-102">EClrEvent-Enumeration</span><span class="sxs-lookup"><span data-stu-id="09e53-102">EClrEvent Enumeration</span></span>
<span data-ttu-id="09e53-103">Beschreibt die Common Language Runtime (CLR)-Ereignisse, für die der Host Rückrufe registrieren kann.</span><span class="sxs-lookup"><span data-stu-id="09e53-103">Describes the common language runtime (CLR) events for which the host can register callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09e53-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="09e53-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    Event_ClrDisabled,  
    Event_DomainUnload,  
    Event_MDAFired,  
    Event_StackOverflow  
} EClrEvent;  
```  
  
## <a name="members"></a><span data-ttu-id="09e53-105">Member</span><span class="sxs-lookup"><span data-stu-id="09e53-105">Members</span></span>  
  
|<span data-ttu-id="09e53-106">Member</span><span class="sxs-lookup"><span data-stu-id="09e53-106">Member</span></span>|<span data-ttu-id="09e53-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="09e53-107">Description</span></span>|  
|------------|-----------------|  
|`Event_ClrDisabled`|<span data-ttu-id="09e53-108">Gibt einen schwerwiegenden CLR-Fehler an.</span><span class="sxs-lookup"><span data-stu-id="09e53-108">Specifies a fatal CLR error.</span></span>|  
|`Event_DomainUnload`|<span data-ttu-id="09e53-109">Gibt das Entladen eines bestimmten an <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="09e53-109">Specifies the unloading of a particular <xref:System.AppDomain>.</span></span>|  
|`Event_MDAFired`|<span data-ttu-id="09e53-110">Gibt an, dass eine MDA-Nachricht (Managed Debug Assistant) generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="09e53-110">Specifies that a Managed Debugging Assistant (MDA) message has been generated.</span></span>|  
|`Event_StackOverflow`|<span data-ttu-id="09e53-111">Gibt an, dass ein Stapelüberlauf Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="09e53-111">Specifies that a stack overflow error has occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09e53-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="09e53-112">Remarks</span></span>  
 <span data-ttu-id="09e53-113">Der Host kann Rückrufe für jeden der Ereignis Typen registrieren, die durch den `EClrEvent` Aufruf der Methoden der [ICLROnEventManager](iclroneventmanager-interface.md) -Schnittstelle beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="09e53-113">The host can register callbacks for any of the event types described by `EClrEvent` by calling methods of the [ICLROnEventManager](iclroneventmanager-interface.md) interface.</span></span> <span data-ttu-id="09e53-114">Der Host erhält einen Zeiger auf diese Schnittstelle, indem er die [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) -Methode aufruft.</span><span class="sxs-lookup"><span data-stu-id="09e53-114">The host gets a pointer to this interface by calling the [ICLRControl::GetCLRManager](iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
 <span data-ttu-id="09e53-115">Das `Event_CLRDisabled` -Ereignis und das- `Event_DomainUnload` Ereignis können mehrmals und aus unterschiedlichen Threads ausgelöst werden, um eine Entladung oder die Deaktivierung der CLR zu signalisieren.</span><span class="sxs-lookup"><span data-stu-id="09e53-115">The `Event_CLRDisabled` and `Event_DomainUnload` events can be raised more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
 <span data-ttu-id="09e53-116">Das- `Event_MDAFired` Ereignis löst die Erstellung einer [MDAInfo](mdainfo-structure.md) -Instanz aus, die die Details der MDA-Nachricht enthält.</span><span class="sxs-lookup"><span data-stu-id="09e53-116">The `Event_MDAFired` event raises the creation of an [MDAInfo](mdainfo-structure.md) instance that contains the details of the MDA message.</span></span> <span data-ttu-id="09e53-117">Weitere Informationen zu MDAs finden Sie unter [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="09e53-117">For more information about MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09e53-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="09e53-118">Requirements</span></span>  
 <span data-ttu-id="09e53-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09e53-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09e53-120">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="09e53-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="09e53-121">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="09e53-121">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="09e53-122">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09e53-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09e53-123">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="09e53-123">See also</span></span>

- [<span data-ttu-id="09e53-124">IActionOnCLREvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="09e53-124">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="09e53-125">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="09e53-125">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="09e53-126">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="09e53-126">Hosting Enumerations</span></span>](hosting-enumerations.md)
