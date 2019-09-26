---
title: CLR_DEBUGGING_PROCESS_FLAGS-Enumeration
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_PROCESS_FLAGS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_PROCESS_FLAG
helpviewer_keywords:
- CLR_DEBUGGING_PROCESS_FLAGS enumeration [.NET Framework debugging]
ms.assetid: 85b85fde-1f87-490b-ba8d-d604670959c3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 292f6953fad0d65b368642543af107c73ec42ab5
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274111"
---
# <a name="clr_debugging_process_flags-enumeration"></a><span data-ttu-id="59c79-102">CLR_DEBUGGING_PROCESS_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="59c79-102">CLR_DEBUGGING_PROCESS_FLAGS Enumeration</span></span>
<span data-ttu-id="59c79-103">Stellt Werte bereit, die von der [ICLRDebugging:: OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) -Methode verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="59c79-103">Provides values that are used by the [ICLRDebugging::OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59c79-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="59c79-104">Syntax</span></span>  
  
```cpp  
typedef enum CLR_DEBUGGING_PROCESS_FLAGS  
{  
   CLR_DEBUGGING_MANAGED_EVENT_PENDING = 1,  
   CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH = 2  
}  CLR_DEBUGGING_PROCESS_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="59c79-105">Member</span><span class="sxs-lookup"><span data-stu-id="59c79-105">Members</span></span>  
  
|<span data-ttu-id="59c79-106">Member</span><span class="sxs-lookup"><span data-stu-id="59c79-106">Member</span></span>|<span data-ttu-id="59c79-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="59c79-107">Description</span></span>|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|<span data-ttu-id="59c79-108">Diese Laufzeit verfügt über ein verwaltetes Debugger-Ereignis, das nicht aufgefangen werden soll.</span><span class="sxs-lookup"><span data-stu-id="59c79-108">This runtime has a non-catch-up managed debugger event to send.</span></span> <span data-ttu-id="59c79-109">Im Abschnitt "Hinweise" finden Sie Informationen zum Unterschied zwischen catch-up-und Non-catch-up-Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="59c79-109">See the Remarks section for the distinction between catch-up and non-catch-up events.</span></span>|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|<span data-ttu-id="59c79-110">Das ausstehende verwaltete Ereignis ist eine <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> -Anforderung.</span><span class="sxs-lookup"><span data-stu-id="59c79-110">The managed event that is pending is a <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59c79-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="59c79-111">Remarks</span></span>  
 <span data-ttu-id="59c79-112">Zu den Aufhol Ereignissen zählen Prozess-, Anwendungs Domänen-, Assembly-, Modul-und Thread Erstellungs Benachrichtigungen, mit denen der Debugger nach dem Anfügen an einen Prozess in den aktuellen Zustand versetzt wird.</span><span class="sxs-lookup"><span data-stu-id="59c79-112">Catch-up events include process, application domain, assembly, module, and thread creation notifications that bring the debugger up to the current state after it has attached to a process.</span></span> <span data-ttu-id="59c79-113">Nicht-catch-Ereignisse, die durch das `CLR_DEBUGGING_MANAGED_EVENT_PENDING` -Flag angegeben werden, schließen alle anderen debuggerereignisse ein, z. b. Ausnahmen und MDA-Benachrichtigungen (Managed Debug Assistant).</span><span class="sxs-lookup"><span data-stu-id="59c79-113">Non-catch-up events, which are indicated by the `CLR_DEBUGGING_MANAGED_EVENT_PENDING` flag, include all other debugger events, such as exceptions and managed debugging assistant (MDA) notifications.</span></span>  
  
 <span data-ttu-id="59c79-114">Mit `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` dem-Flag kann die Laufzeit zwischen einer Beendigungs Ausnahme und einer Anforderung zum Anfügen eines verwalteten Debuggers unterscheiden, der abgebrochen werden kann.</span><span class="sxs-lookup"><span data-stu-id="59c79-114">The `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` flag enables the runtime to differentiate between a terminating exception and a request to attach a managed debugger that can be canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59c79-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="59c79-115">Requirements</span></span>  
 <span data-ttu-id="59c79-116">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59c79-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59c79-117">**Header:** MetaHost. idl, MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="59c79-117">**Header:** Metahost.idl, Metahost.h</span></span>  
  
 <span data-ttu-id="59c79-118">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59c79-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59c79-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59c79-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59c79-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="59c79-120">See also</span></span>

- [<span data-ttu-id="59c79-121">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="59c79-121">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="59c79-122">Debuggen</span><span class="sxs-lookup"><span data-stu-id="59c79-122">Debugging</span></span>](index.md)
