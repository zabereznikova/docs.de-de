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
ms.openlocfilehash: dd148d23d6e29f03052d3bbf1fcd5d02fb332a0a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729849"
---
# <a name="clr_debugging_process_flags-enumeration"></a><span data-ttu-id="87598-102">CLR_DEBUGGING_PROCESS_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="87598-102">CLR_DEBUGGING_PROCESS_FLAGS Enumeration</span></span>

<span data-ttu-id="87598-103">Stellt Werte bereit, die von der [ICLRDebugging:: OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) -Methode verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="87598-103">Provides values that are used by the [ICLRDebugging::OpenVirtualProcess](iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87598-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="87598-104">Syntax</span></span>  
  
```cpp  
typedef enum CLR_DEBUGGING_PROCESS_FLAGS  
{  
   CLR_DEBUGGING_MANAGED_EVENT_PENDING = 1,  
   CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH = 2  
}  CLR_DEBUGGING_PROCESS_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="87598-105">Member</span><span class="sxs-lookup"><span data-stu-id="87598-105">Members</span></span>  
  
|<span data-ttu-id="87598-106">Member</span><span class="sxs-lookup"><span data-stu-id="87598-106">Member</span></span>|<span data-ttu-id="87598-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="87598-107">Description</span></span>|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|<span data-ttu-id="87598-108">Diese Laufzeit verfügt über ein verwaltetes Debugger-Ereignis, das nicht aufgefangen werden soll.</span><span class="sxs-lookup"><span data-stu-id="87598-108">This runtime has a non-catch-up managed debugger event to send.</span></span> <span data-ttu-id="87598-109">Im Abschnitt "Hinweise" finden Sie Informationen zum Unterschied zwischen catch-up-und Non-catch-up-Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="87598-109">See the Remarks section for the distinction between catch-up and non-catch-up events.</span></span>|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|<span data-ttu-id="87598-110">Das ausstehende verwaltete Ereignis ist eine- <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> Anforderung.</span><span class="sxs-lookup"><span data-stu-id="87598-110">The managed event that is pending is a <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87598-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="87598-111">Remarks</span></span>  

 <span data-ttu-id="87598-112">Zu den Aufhol Ereignissen zählen Prozess-, Anwendungs Domänen-, Assembly-, Modul-und Thread Erstellungs Benachrichtigungen, mit denen der Debugger nach dem Anfügen an einen Prozess in den aktuellen Zustand versetzt wird.</span><span class="sxs-lookup"><span data-stu-id="87598-112">Catch-up events include process, application domain, assembly, module, and thread creation notifications that bring the debugger up to the current state after it has attached to a process.</span></span> <span data-ttu-id="87598-113">Nicht-catch-Ereignisse, die durch das-Flag angegeben werden `CLR_DEBUGGING_MANAGED_EVENT_PENDING` , schließen alle anderen debuggerereignisse ein, z. b. Ausnahmen und MDA-Benachrichtigungen (Managed Debug Assistant).</span><span class="sxs-lookup"><span data-stu-id="87598-113">Non-catch-up events, which are indicated by the `CLR_DEBUGGING_MANAGED_EVENT_PENDING` flag, include all other debugger events, such as exceptions and managed debugging assistant (MDA) notifications.</span></span>  
  
 <span data-ttu-id="87598-114">`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`Mit dem-Flag kann die Laufzeit zwischen einer Beendigungs Ausnahme und einer Anforderung zum Anfügen eines verwalteten Debuggers unterscheiden, der abgebrochen werden kann.</span><span class="sxs-lookup"><span data-stu-id="87598-114">The `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` flag enables the runtime to differentiate between a terminating exception and a request to attach a managed debugger that can be canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87598-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="87598-115">Requirements</span></span>  

 <span data-ttu-id="87598-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87598-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87598-117">**Header:** MetaHost. idl, MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="87598-117">**Header:** Metahost.idl, Metahost.h</span></span>  
  
 <span data-ttu-id="87598-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87598-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87598-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87598-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87598-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="87598-120">See also</span></span>

- [<span data-ttu-id="87598-121">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="87598-121">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="87598-122">Debuggen</span><span class="sxs-lookup"><span data-stu-id="87598-122">Debugging</span></span>](index.md)
