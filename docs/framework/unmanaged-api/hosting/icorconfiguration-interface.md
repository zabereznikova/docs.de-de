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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 63699f0af69b3a7623c5e9da156c2ff8ae83ccfc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437512"
---
# <a name="icorconfiguration-interface"></a><span data-ttu-id="ce2af-102">ICorConfiguration-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ce2af-102">ICorConfiguration Interface</span></span>
<span data-ttu-id="ce2af-103">Stellt Methoden für die common Language Runtime (CLR) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ce2af-103">Provides methods for configuring the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ce2af-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ce2af-104">Methods</span></span>  
  
|<span data-ttu-id="ce2af-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ce2af-105">Method</span></span>|<span data-ttu-id="ce2af-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce2af-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ce2af-107">AddDebuggerSpecialThread-Methode</span><span class="sxs-lookup"><span data-stu-id="ce2af-107">AddDebuggerSpecialThread Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-adddebuggerspecialthread-method.md)|<span data-ttu-id="ce2af-108">Zeigt den Debugdiensten an, dass ein bestimmter Thread fortgesetzt werden, während der Debugger eine Anwendung, die während des Szenarios des verwalteten oder nicht verwalteten Debuggens beendet hat darf.</span><span class="sxs-lookup"><span data-stu-id="ce2af-108">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>|  
|[<span data-ttu-id="ce2af-109">SetDebuggerThreadControl-Methode</span><span class="sxs-lookup"><span data-stu-id="ce2af-109">SetDebuggerThreadControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setdebuggerthreadcontrol-method.md)|<span data-ttu-id="ce2af-110">Legt die Rückrufschnittstelle, die der Debugdienste für das Debuggen aufrufen, wenn CLR-Threads blockiert und freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ce2af-110">Sets the callback interface that the debugging services will call as CLR threads are blocked and unblocked for debugging.</span></span>|  
|[<span data-ttu-id="ce2af-111">SetGCHostControl-Methode</span><span class="sxs-lookup"><span data-stu-id="ce2af-111">SetGCHostControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgchostcontrol-method.md)|<span data-ttu-id="ce2af-112">Legt die Rückrufschnittstelle vom Garbage Collector verwendet werden, um den Host zum Ändern der Grenzen des virtuellen Arbeitsspeichers anzufordern.</span><span class="sxs-lookup"><span data-stu-id="ce2af-112">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>|  
|[<span data-ttu-id="ce2af-113">SetGCThreadControl-Methode</span><span class="sxs-lookup"><span data-stu-id="ce2af-113">SetGCThreadControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgcthreadcontrol-method.md)|<span data-ttu-id="ce2af-114">Legt die Rückrufschnittstelle für die Planung von Threads für nicht-Runtime-Aufgaben, die andernfalls für eine Garbagecollection blockiert werden würde.</span><span class="sxs-lookup"><span data-stu-id="ce2af-114">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ce2af-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ce2af-115">Requirements</span></span>  
 <span data-ttu-id="ce2af-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce2af-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce2af-117">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ce2af-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ce2af-118">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ce2af-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ce2af-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce2af-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce2af-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce2af-120">See Also</span></span>  
 [<span data-ttu-id="ce2af-121">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ce2af-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="ce2af-122">CorRuntimeHost-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="ce2af-122">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
