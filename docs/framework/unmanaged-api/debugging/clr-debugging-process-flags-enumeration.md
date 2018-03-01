---
title: CLR_DEBUGGING_PROCESS_FLAGS-Enumeration
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4c6d66f9a11f28ca572e0f1eddc74f3a5197a19d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="clrdebuggingprocessflags-enumeration"></a><span data-ttu-id="f1d07-102">CLR_DEBUGGING_PROCESS_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="f1d07-102">CLR_DEBUGGING_PROCESS_FLAGS Enumeration</span></span>
<span data-ttu-id="f1d07-103">Enthält Werte, mit denen, die [ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="f1d07-103">Provides values that are used by the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1d07-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f1d07-104">Syntax</span></span>  
  
```  
typedef enum CLR_DEBUGGING_PROCESS_FLAGS  
{  
   CLR_DEBUGGING_MANAGED_EVENT_PENDING = 1,  
   CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH = 2  
}  CLR_DEBUGGING_PROCESS_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="f1d07-105">Member</span><span class="sxs-lookup"><span data-stu-id="f1d07-105">Members</span></span>  
  
|<span data-ttu-id="f1d07-106">Member</span><span class="sxs-lookup"><span data-stu-id="f1d07-106">Member</span></span>|<span data-ttu-id="f1d07-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f1d07-107">Description</span></span>|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|<span data-ttu-id="f1d07-108">Diese Laufzeit ist ein verwalteter Debugger Catch-nach-oben-Ereignis zu senden.</span><span class="sxs-lookup"><span data-stu-id="f1d07-108">This runtime has a non-catch-up managed debugger event to send.</span></span> <span data-ttu-id="f1d07-109">Finden Sie im Abschnitt "Hinweise" für die Unterscheidung zwischen hervorgehobene und Catch-nach-oben-Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="f1d07-109">See the Remarks section for the distinction between catch-up and non-catch-up events.</span></span>|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|<span data-ttu-id="f1d07-110">Das verwaltete Ereignis aussteht ist eine <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> Anforderung.</span><span class="sxs-lookup"><span data-stu-id="f1d07-110">The managed event that is pending is a <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1d07-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f1d07-111">Remarks</span></span>  
 <span data-ttu-id="f1d07-112">Synchronisieren von Ereignissen enthalten Prozess, die Anwendungsdomäne, Assembly, Modul und Thread Erstellung Benachrichtigungen, die den Debugger bis zu den aktuellen Zustand zu bringen, nach dem Anfügen an einen Prozess hat.</span><span class="sxs-lookup"><span data-stu-id="f1d07-112">Catch-up events include process, application domain, assembly, module, and thread creation notifications that bring the debugger up to the current state after it has attached to a process.</span></span> <span data-ttu-id="f1d07-113">Nicht-Catch-Up-Ereignisse, die ersichtlich sind die `CLR_DEBUGGING_MANAGED_EVENT_PENDING` kennzeichnen, schließen Sie alle anderen Debugger-Ereignissen, z. B. Ausnahmen und managed debugging Assistant, Assistent für (verwaltetes Debuggen MDA) Benachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="f1d07-113">Non-catch-up events, which are indicated by the `CLR_DEBUGGING_MANAGED_EVENT_PENDING` flag, include all other debugger events, such as exceptions and managed debugging assistant (MDA) notifications.</span></span>  
  
 <span data-ttu-id="f1d07-114">Die `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` Flag kann die Laufzeit eine abschließende Ausnahme und eine Anforderung an einen verwalteten Debugger anfügen, die abgebrochen werden kann, unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="f1d07-114">The `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` flag enables the runtime to differentiate between a terminating exception and a request to attach a managed debugger that can be canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1d07-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f1d07-115">Requirements</span></span>  
 <span data-ttu-id="f1d07-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1d07-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1d07-117">**Header:** Metahost.idl, Metahost.h</span><span class="sxs-lookup"><span data-stu-id="f1d07-117">**Header:** Metahost.idl, Metahost.h</span></span>  
  
 <span data-ttu-id="f1d07-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1d07-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1d07-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1d07-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1d07-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1d07-120">See Also</span></span>  
 [<span data-ttu-id="f1d07-121">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="f1d07-121">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="f1d07-122">Debuggen</span><span class="sxs-lookup"><span data-stu-id="f1d07-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
