---
title: ICorConfiguration-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorConfiguration
helpviewer_keywords:
- ICorConfiguration interface [.NET Framework hosting]
ms.assetid: aaf96116-372b-4538-afb1-9e0fcdac1f98
topic_type:
- apiref
ms.openlocfilehash: fa8d15bc8e504a57d5cc87c170a3a5b022798add
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715783"
---
# <a name="icorconfiguration-interface"></a><span data-ttu-id="374c3-102">ICorConfiguration-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="374c3-102">ICorConfiguration Interface</span></span>

<span data-ttu-id="374c3-103">Stellt Methoden zum Konfigurieren des Common Language Runtime (CLR) bereit.</span><span class="sxs-lookup"><span data-stu-id="374c3-103">Provides methods for configuring the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="374c3-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="374c3-104">Methods</span></span>  
  
|<span data-ttu-id="374c3-105">Methode</span><span class="sxs-lookup"><span data-stu-id="374c3-105">Method</span></span>|<span data-ttu-id="374c3-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="374c3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="374c3-107">AddDebuggerSpecialThread-Methode</span><span class="sxs-lookup"><span data-stu-id="374c3-107">AddDebuggerSpecialThread Method</span></span>](icorconfiguration-adddebuggerspecialthread-method.md)|<span data-ttu-id="374c3-108">Gibt den Debugdiensten an, dass ein bestimmter Thread weiter ausgeführt werden darf, während der Debugger eine Anwendung während verwalteter oder nicht verwalteter debuggingszenarien beendet hat.</span><span class="sxs-lookup"><span data-stu-id="374c3-108">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>|  
|[<span data-ttu-id="374c3-109">SetDebuggerThreadControl-Methode</span><span class="sxs-lookup"><span data-stu-id="374c3-109">SetDebuggerThreadControl Method</span></span>](icorconfiguration-setdebuggerthreadcontrol-method.md)|<span data-ttu-id="374c3-110">Legt die Rückruf Schnittstelle fest, die von den Debugdiensten aufgerufen wird, wenn CLR-Threads blockiert und für das Debuggen blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="374c3-110">Sets the callback interface that the debugging services will call as CLR threads are blocked and unblocked for debugging.</span></span>|  
|[<span data-ttu-id="374c3-111">SetGCHostControl-Methode</span><span class="sxs-lookup"><span data-stu-id="374c3-111">SetGCHostControl Method</span></span>](icorconfiguration-setgchostcontrol-method.md)|<span data-ttu-id="374c3-112">Legt die Rückruf Schnittstelle fest, die vom Garbage Collector verwendet werden soll, um den Host zum Ändern der Grenzwerte für den virtuellen Arbeitsspeicher anzufordern.</span><span class="sxs-lookup"><span data-stu-id="374c3-112">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>|  
|[<span data-ttu-id="374c3-113">SetGCThreadControl-Methode</span><span class="sxs-lookup"><span data-stu-id="374c3-113">SetGCThreadControl Method</span></span>](icorconfiguration-setgcthreadcontrol-method.md)|<span data-ttu-id="374c3-114">Legt die Rückruf Schnittstelle für das Planen von Threads für nicht-Lauf Zeit Aufgaben fest, die andernfalls für eine Garbage Collection blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="374c3-114">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="374c3-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="374c3-115">Requirements</span></span>  

 <span data-ttu-id="374c3-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="374c3-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="374c3-117">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="374c3-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="374c3-118">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="374c3-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="374c3-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="374c3-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="374c3-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="374c3-120">See also</span></span>

- [<span data-ttu-id="374c3-121">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="374c3-121">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="374c3-122">CorRuntimeHost-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="374c3-122">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)
