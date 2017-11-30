---
title: MDAInfo-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: MDAInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: MDAInfo
helpviewer_keywords: MDAInfo structure [.NET Framework hosting]
ms.assetid: fb8c14f7-d461-43d1-8b47-adb6723b9b93
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d303bcbee0b0c769fe2bc45663356b759fc91669
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="mdainfo-structure"></a><span data-ttu-id="dc314-102">MDAInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="dc314-102">MDAInfo Structure</span></span>
<span data-ttu-id="dc314-103">Enthält Informationen über die `Event_MDAFired` -Ereignis, das die Erstellung von ein Assistent für verwaltetes Debuggen (MDA) ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="dc314-103">Provides details about the `Event_MDAFired` event, which triggers the creation of a managed debugging assistant (MDA).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc314-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dc314-104">Syntax</span></span>  
  
```  
typedef struct _MDAInfo {  
    LPCWSTR  lpMDACaption;  
    LPCWSTR  lpMDAMessage  
} MDAInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="dc314-105">Member</span><span class="sxs-lookup"><span data-stu-id="dc314-105">Members</span></span>  
  
|<span data-ttu-id="dc314-106">Member</span><span class="sxs-lookup"><span data-stu-id="dc314-106">Member</span></span>|<span data-ttu-id="dc314-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dc314-107">Description</span></span>|  
|------------|-----------------|  
|`lpMDACaption`|<span data-ttu-id="dc314-108">Der Titel des aktuellen MDA.</span><span class="sxs-lookup"><span data-stu-id="dc314-108">The title of the current MDA.</span></span> <span data-ttu-id="dc314-109">Der Titel beschreibt die Art des Fehlers, der ausgelöst der `Event_MDAFired` Ereignis.</span><span class="sxs-lookup"><span data-stu-id="dc314-109">The title describes the kind of failure that triggered the `Event_MDAFired` event.</span></span>|  
|`lpMDAMessage`|<span data-ttu-id="dc314-110">Die Ausgabenachricht, die von der aktuellen MDA bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="dc314-110">The output message provided by the current MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc314-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dc314-111">Remarks</span></span>  
 <span data-ttu-id="dc314-112">Assistenten für verwaltetes Debuggen (MDAs) sind in Verbindung mit der common Language Runtime (CLR), um Aufgaben wie das Identifizieren von ungültiger Bedingungen arbeiten im Ausführungsmodul Laufzeit debughilfen oder Dump-zusätzliche Informationen über den Status der Sicherungen der Modul.</span><span class="sxs-lookup"><span data-stu-id="dc314-112">Managed debugging assistants (MDAs) are debugging aids that work in conjunction with the common language runtime (CLR) to perform tasks such as identifying invalid conditions in the runtime execution engine or dumping additional information about the state of the engine.</span></span> <span data-ttu-id="dc314-113">MDAs generieren XML-Meldungen über Ereignisse, die andernfalls schwer abfangen.</span><span class="sxs-lookup"><span data-stu-id="dc314-113">MDAs generate XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="dc314-114">Sie sind besonders nützlich zum Debuggen von Übergängen zwischen verwaltetem und nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="dc314-114">They are especially useful for debugging transitions between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="dc314-115">Die Common Language Runtime verwendet die folgenden Schritte aus, wenn ein Ereignis, das die Erstellung eines MDA-Trigger ausgelöst wird:</span><span class="sxs-lookup"><span data-stu-id="dc314-115">The runtime takes the following steps when an event that triggers the creation of an MDA is fired:</span></span>  
  
-   <span data-ttu-id="dc314-116">Wenn der Host nicht registriert wurde ein [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) Instanz durch Aufrufen [ICLROnEventManager:: RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) benachrichtigt zu werden ein `Event_MDAFired` -Ereignis die Laufzeit fortgesetzt wird, mit dessen Standardverhalten nicht gehostet.</span><span class="sxs-lookup"><span data-stu-id="dc314-116">If the host has not registered an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) instance by calling [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) to be notified of an `Event_MDAFired` event, the runtime proceeds with its default, non-hosted behavior.</span></span>  
  
-   <span data-ttu-id="dc314-117">Wenn der Host einen Handler für dieses Ereignis registriert hat, überprüft die Common Language Runtime, ob ein Debugger an den Prozess angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="dc314-117">If the host has registered a handler for this event, the runtime checks to see whether a debugger is attached to the process.</span></span> <span data-ttu-id="dc314-118">Wenn dies der Fall, wird die Common Language Runtime im Debugger unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="dc314-118">If it is, the runtime breaks into the debugger.</span></span> <span data-ttu-id="dc314-119">Wenn der Debugger weiterhin auftritt, ruft er auf den Host.</span><span class="sxs-lookup"><span data-stu-id="dc314-119">When the debugger continues, it calls into the host.</span></span> <span data-ttu-id="dc314-120">Wenn kein Debugger angefügt ist, ruft die Runtime `IActionOnCLREvent::OnEvent` und übergibt einen Zeiger auf eine `MDAInfo` -Instanz als der `data` Parameter.</span><span class="sxs-lookup"><span data-stu-id="dc314-120">If no debugger is attached, the runtime calls `IActionOnCLREvent::OnEvent` and passes a pointer to an `MDAInfo` instance as the `data` parameter.</span></span>  
  
 <span data-ttu-id="dc314-121">Der Host kann auswählen, um MDAs zu aktivieren und benachrichtigt, wenn ein MDA aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="dc314-121">The host can choose to activate MDAs and to be notified when an MDA is activated.</span></span> <span data-ttu-id="dc314-122">Dies ermöglicht dem Host ein Standardverhalten überschreiben und den verwalteten Thread abgebrochen, der das Ereignis, um zu verhindern, dass es den Prozessstatus beschädigen ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="dc314-122">This gives the host an opportunity to override default behavior and to abort the managed thread that raised the event, to prevent it from corrupting the process state.</span></span> <span data-ttu-id="dc314-123">Weitere Informationen zum Verwenden von MDAs finden Sie unter [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="dc314-123">For more information about using MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc314-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dc314-124">Requirements</span></span>  
 <span data-ttu-id="dc314-125">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc314-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc314-126">**Header:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="dc314-126">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="dc314-127">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="dc314-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dc314-128">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc314-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc314-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc314-129">See Also</span></span>  
 [<span data-ttu-id="dc314-130">Hosten von Strukturen</span><span class="sxs-lookup"><span data-stu-id="dc314-130">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [<span data-ttu-id="dc314-131">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="dc314-131">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
