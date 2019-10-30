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
ms.openlocfilehash: 9a2f513d40d722f1b0aad823ac7c0d93bda5615f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123264"
---
# <a name="mdainfo-structure"></a><span data-ttu-id="d4c77-102">MDAInfo-Struktur</span><span class="sxs-lookup"><span data-stu-id="d4c77-102">MDAInfo Structure</span></span>
<span data-ttu-id="d4c77-103">Stellt Details zum `Event_MDAFired` Ereignis bereit, das die Erstellung eines Assistenten für verwaltetes Debuggen (MDA) auslöst.</span><span class="sxs-lookup"><span data-stu-id="d4c77-103">Provides details about the `Event_MDAFired` event, which triggers the creation of a managed debugging assistant (MDA).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4c77-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d4c77-104">Syntax</span></span>  
  
```cpp  
typedef struct _MDAInfo {  
    LPCWSTR  lpMDACaption;  
    LPCWSTR  lpMDAMessage  
} MDAInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="d4c77-105">Member</span><span class="sxs-lookup"><span data-stu-id="d4c77-105">Members</span></span>  
  
|<span data-ttu-id="d4c77-106">Member</span><span class="sxs-lookup"><span data-stu-id="d4c77-106">Member</span></span>|<span data-ttu-id="d4c77-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d4c77-107">Description</span></span>|  
|------------|-----------------|  
|`lpMDACaption`|<span data-ttu-id="d4c77-108">Der Titel des aktuellen MDA.</span><span class="sxs-lookup"><span data-stu-id="d4c77-108">The title of the current MDA.</span></span> <span data-ttu-id="d4c77-109">Der Titel beschreibt die Art des Fehlers, der das `Event_MDAFired` Ereignis ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="d4c77-109">The title describes the kind of failure that triggered the `Event_MDAFired` event.</span></span>|  
|`lpMDAMessage`|<span data-ttu-id="d4c77-110">Die vom aktuellen MDA bereitgestellte Ausgabe Meldung.</span><span class="sxs-lookup"><span data-stu-id="d4c77-110">The output message provided by the current MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4c77-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d4c77-111">Remarks</span></span>  
 <span data-ttu-id="d4c77-112">Assistenten für verwaltetes Debuggen (MDAs) sind Debugginghilfen, die in Verbindung mit dem Common Language Runtime (CLR) funktionieren, um Aufgaben wie das Identifizieren von ungültigen Bedingungen in der Lauf Zeit Ausführungs-Engine oder das Sichern zusätzlicher Informationen über den Zustand des ge.</span><span class="sxs-lookup"><span data-stu-id="d4c77-112">Managed debugging assistants (MDAs) are debugging aids that work in conjunction with the common language runtime (CLR) to perform tasks such as identifying invalid conditions in the runtime execution engine or dumping additional information about the state of the engine.</span></span> <span data-ttu-id="d4c77-113">MDAs generiert XML-Meldungen über Ereignisse, die andernfalls schwierig zu erfassen sind.</span><span class="sxs-lookup"><span data-stu-id="d4c77-113">MDAs generate XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="d4c77-114">Sie sind besonders nützlich zum Debuggen von Übergängen zwischen verwaltetem und nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="d4c77-114">They are especially useful for debugging transitions between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="d4c77-115">Die Laufzeit führt die folgenden Schritte aus, wenn ein Ereignis ausgelöst wird, das die Erstellung eines MDA auslöst:</span><span class="sxs-lookup"><span data-stu-id="d4c77-115">The runtime takes the following steps when an event that triggers the creation of an MDA is fired:</span></span>  
  
- <span data-ttu-id="d4c77-116">Wenn der Host keine [iaktiononclrevent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) -Instanz durch Aufrufen von [ICLROnEventManager:: registeraktiononevent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) registriert hat, um über ein `Event_MDAFired` Ereignis benachrichtigt zu werden, wird die Laufzeit mit dem standardmäßigen, nicht gehosteten Verhalten fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="d4c77-116">If the host has not registered an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) instance by calling [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) to be notified of an `Event_MDAFired` event, the runtime proceeds with its default, non-hosted behavior.</span></span>  
  
- <span data-ttu-id="d4c77-117">Wenn der Host einen Handler für dieses Ereignis registriert hat, prüft die Laufzeit, ob ein Debugger an den Prozess angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="d4c77-117">If the host has registered a handler for this event, the runtime checks to see whether a debugger is attached to the process.</span></span> <span data-ttu-id="d4c77-118">Wenn dies der Fall ist, unterbricht die Laufzeit den Debugger.</span><span class="sxs-lookup"><span data-stu-id="d4c77-118">If it is, the runtime breaks into the debugger.</span></span> <span data-ttu-id="d4c77-119">Wenn der Debugger fortgesetzt wird, ruft er den Host auf.</span><span class="sxs-lookup"><span data-stu-id="d4c77-119">When the debugger continues, it calls into the host.</span></span> <span data-ttu-id="d4c77-120">Wenn kein Debugger angefügt ist, ruft die Laufzeit `IActionOnCLREvent::OnEvent` auf und übergibt einen Zeiger auf eine `MDAInfo` Instanz als `data` Parameter.</span><span class="sxs-lookup"><span data-stu-id="d4c77-120">If no debugger is attached, the runtime calls `IActionOnCLREvent::OnEvent` and passes a pointer to an `MDAInfo` instance as the `data` parameter.</span></span>  
  
 <span data-ttu-id="d4c77-121">Der Host kann MDAs aktivieren und benachrichtigt werden, wenn ein MDA aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="d4c77-121">The host can choose to activate MDAs and to be notified when an MDA is activated.</span></span> <span data-ttu-id="d4c77-122">Dadurch erhält der Host die Möglichkeit, das Standardverhalten zu überschreiben und den verwalteten Thread abzubrechen, der das Ereignis ausgelöst hat, um zu verhindern, dass der Prozessstatus beschädigt wird.</span><span class="sxs-lookup"><span data-stu-id="d4c77-122">This gives the host an opportunity to override default behavior and to abort the managed thread that raised the event, to prevent it from corrupting the process state.</span></span> <span data-ttu-id="d4c77-123">Weitere Informationen zur Verwendung von MDAs finden Sie unter [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="d4c77-123">For more information about using MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4c77-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d4c77-124">Requirements</span></span>  
 <span data-ttu-id="d4c77-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4c77-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4c77-126">**Header:** Mscoree. idl</span><span class="sxs-lookup"><span data-stu-id="d4c77-126">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="d4c77-127">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d4c77-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d4c77-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4c77-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4c77-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4c77-129">See also</span></span>

- [<span data-ttu-id="d4c77-130">Hosten von Strukturen</span><span class="sxs-lookup"><span data-stu-id="d4c77-130">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="d4c77-131">Diagnosing Errors with Managed Debugging Assistants (Fehlerdiagnose mit den Assistenten für verwaltetes Debugging)</span><span class="sxs-lookup"><span data-stu-id="d4c77-131">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
