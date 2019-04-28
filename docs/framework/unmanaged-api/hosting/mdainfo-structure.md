---
title: MDAInfo-Struktur
ms.date: 03/30/2017
api_name:
- MDAInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- MDAInfo
helpviewer_keywords:
- MDAInfo structure [.NET Framework hosting]
ms.assetid: fb8c14f7-d461-43d1-8b47-adb6723b9b93
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3be6f2b9454ed2f74d2cc6792cd9aaa2c25215db
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765205"
---
# <a name="mdainfo-structure"></a><span data-ttu-id="eae66-102">MDAInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="eae66-102">MDAInfo Structure</span></span>
<span data-ttu-id="eae66-103">Enthält Informationen über die `Event_MDAFired` -Ereignis, das die Erstellung einer-Assistent für verwaltetes Debuggen (MDA) ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="eae66-103">Provides details about the `Event_MDAFired` event, which triggers the creation of a managed debugging assistant (MDA).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eae66-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eae66-104">Syntax</span></span>  
  
```  
typedef struct _MDAInfo {  
    LPCWSTR  lpMDACaption;  
    LPCWSTR  lpMDAMessage  
} MDAInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="eae66-105">Member</span><span class="sxs-lookup"><span data-stu-id="eae66-105">Members</span></span>  
  
|<span data-ttu-id="eae66-106">Member</span><span class="sxs-lookup"><span data-stu-id="eae66-106">Member</span></span>|<span data-ttu-id="eae66-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eae66-107">Description</span></span>|  
|------------|-----------------|  
|`lpMDACaption`|<span data-ttu-id="eae66-108">Der Titel des aktuellen MDA.</span><span class="sxs-lookup"><span data-stu-id="eae66-108">The title of the current MDA.</span></span> <span data-ttu-id="eae66-109">Der Titel beschreibt die Art des Fehlers, der ausgelöst der `Event_MDAFired` Ereignis.</span><span class="sxs-lookup"><span data-stu-id="eae66-109">The title describes the kind of failure that triggered the `Event_MDAFired` event.</span></span>|  
|`lpMDAMessage`|<span data-ttu-id="eae66-110">Die Ausgabenachricht, die von der aktuellen MDA bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="eae66-110">The output message provided by the current MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eae66-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eae66-111">Remarks</span></span>  
 <span data-ttu-id="eae66-112">Verwaltetes Debuggen (MDA) Debugginghilfen, die in Verbindung mit der common Language Runtime (CLR) zum Ausführen von Aufgaben wie das Identifizieren von ungültiger Bedingungen funktionieren in der Common Language Runtime-ausführungs-Engine oder zusätzliche Informationen über den Status der Ausgabe der -Engine.</span><span class="sxs-lookup"><span data-stu-id="eae66-112">Managed debugging assistants (MDAs) are debugging aids that work in conjunction with the common language runtime (CLR) to perform tasks such as identifying invalid conditions in the runtime execution engine or dumping additional information about the state of the engine.</span></span> <span data-ttu-id="eae66-113">MDAs generieren XML-Nachrichten über Ereignisse, die andernfalls nur schwer abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="eae66-113">MDAs generate XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="eae66-114">Sie sind besonders nützlich für das Debuggen von Übergängen zwischen verwaltetem und nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="eae66-114">They are especially useful for debugging transitions between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="eae66-115">Die Common Language Runtime verwendet die folgenden Schritte aus, wenn ein Ereignis, das die Erstellung eines MDA wird ausgelöst, die ausgelöst wird:</span><span class="sxs-lookup"><span data-stu-id="eae66-115">The runtime takes the following steps when an event that triggers the creation of an MDA is fired:</span></span>  
  
- <span data-ttu-id="eae66-116">Wenn der Host nicht registriert wurde ein [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) Instanz durch den Aufruf [ICLROnEventManager:: RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) benachrichtigt werden sollen ein `Event_MDAFired` Ereignis die Laufzeit fortgesetzt wird, mit der standardmäßig nicht gehosteten Verhalten.</span><span class="sxs-lookup"><span data-stu-id="eae66-116">If the host has not registered an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) instance by calling [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) to be notified of an `Event_MDAFired` event, the runtime proceeds with its default, non-hosted behavior.</span></span>  
  
- <span data-ttu-id="eae66-117">Wenn der Host einen Handler für dieses Ereignis registriert hat, überprüft die Laufzeit, um festzustellen, ob ein Debugger an den Prozess angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="eae66-117">If the host has registered a handler for this event, the runtime checks to see whether a debugger is attached to the process.</span></span> <span data-ttu-id="eae66-118">Wenn es sich handelt, unterbricht die Runtime den Debugger.</span><span class="sxs-lookup"><span data-stu-id="eae66-118">If it is, the runtime breaks into the debugger.</span></span> <span data-ttu-id="eae66-119">Wenn der Debugger weiterhin auftritt, wird mit dem Host.</span><span class="sxs-lookup"><span data-stu-id="eae66-119">When the debugger continues, it calls into the host.</span></span> <span data-ttu-id="eae66-120">Wenn kein Debugger angefügt ist, ruft die Runtime `IActionOnCLREvent::OnEvent` und übergibt einen Zeiger auf ein `MDAInfo` -Instanz als die `data` Parameter.</span><span class="sxs-lookup"><span data-stu-id="eae66-120">If no debugger is attached, the runtime calls `IActionOnCLREvent::OnEvent` and passes a pointer to an `MDAInfo` instance as the `data` parameter.</span></span>  
  
 <span data-ttu-id="eae66-121">Der Host kann auswählen, um MDAs zu aktivieren und benachrichtigt werden, wenn ein MDA aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="eae66-121">The host can choose to activate MDAs and to be notified when an MDA is activated.</span></span> <span data-ttu-id="eae66-122">Dies ermöglicht dem Host ein Standardverhalten außer Kraft setzen und den verwalteten Thread abzubrechen, der das Ereignis, um zu verhindern, dass sie den Verarbeitungsstatus beschädigen ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="eae66-122">This gives the host an opportunity to override default behavior and to abort the managed thread that raised the event, to prevent it from corrupting the process state.</span></span> <span data-ttu-id="eae66-123">Weitere Informationen zum Verwenden von MDAs finden Sie unter [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="eae66-123">For more information about using MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eae66-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eae66-124">Requirements</span></span>  
 <span data-ttu-id="eae66-125">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eae66-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eae66-126">**Header:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="eae66-126">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="eae66-127">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="eae66-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eae66-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eae66-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eae66-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eae66-129">See also</span></span>

- [<span data-ttu-id="eae66-130">Hosten von Strukturen</span><span class="sxs-lookup"><span data-stu-id="eae66-130">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="eae66-131">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="eae66-131">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
