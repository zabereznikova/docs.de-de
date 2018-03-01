---
title: ETaskType-Enumeration
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
- ETaskType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ETaskType
helpviewer_keywords:
- ETaskType enumeration [.NET Framework hosting]
ms.assetid: aa527b31-89d4-41f2-ad6f-63b76950b7df
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a7973b8cbd49858daaf6f08d55c7d9f60f687a72
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="etasktype-enumeration"></a><span data-ttu-id="58e4d-102">ETaskType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="58e4d-102">ETaskType Enumeration</span></span>
<span data-ttu-id="58e4d-103">Enthält Werte, die den Typ der Aufgabe angeben, indem Sie entweder dargestellt wird, ein [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) oder ein [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="58e4d-103">Contains values that indicate the type of task that is represented by either an [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) or an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58e4d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="58e4d-104">Syntax</span></span>  
  
```  
typedef enum ETaskType {  
    TT_DEBUGGERHELPER           = 0x1,  
    TT_GC                       = 0x2,  
    TT_FINALIZER                = 0x4,  
    TT_THREADPOOL_TIMER         = 0x8,  
    TT_THREADPOOL_GATE          = 0x10,  
    TT_THREADPOOL_WORKER        = 0x20,  
    TT_THREADPOOL_IOCOMPLETION  = 0x40,  
    TT_ADUNLOAD                 = 0x80,  
    TT_USER                     = 0x100,  
    TT_THREADPOOL_WAIT          = 0x200,  
    TT_UNKNOWN                  = 0x80000000  
} ETaskType;  
```  
  
## <a name="members"></a><span data-ttu-id="58e4d-105">Member</span><span class="sxs-lookup"><span data-stu-id="58e4d-105">Members</span></span>  
  
|<span data-ttu-id="58e4d-106">Member</span><span class="sxs-lookup"><span data-stu-id="58e4d-106">Member</span></span>|<span data-ttu-id="58e4d-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58e4d-107">Description</span></span>|  
|------------|-----------------|  
|`TT_ADUNLOAD`|<span data-ttu-id="58e4d-108">Die Schnittstelle stellt einen Anwendung Domäne entladen-Task dar.</span><span class="sxs-lookup"><span data-stu-id="58e4d-108">The interface represents an application domain unloading task.</span></span>|  
|`TT_DEBUGGERHELPER`|<span data-ttu-id="58e4d-109">Die Schnittstelle stellt einen Debugger Helper-Task dar.</span><span class="sxs-lookup"><span data-stu-id="58e4d-109">The interface represents a debugger helper task.</span></span>|  
|`TT_FINALIZER`|<span data-ttu-id="58e4d-110">Die Schnittstelle stellt einen Finalizer-Task dar.</span><span class="sxs-lookup"><span data-stu-id="58e4d-110">The interface represents a finalizer task.</span></span>|  
|`TT_GC`|<span data-ttu-id="58e4d-111">Die Schnittstelle stellt eine Garbage Collection-Aufgabe dar.</span><span class="sxs-lookup"><span data-stu-id="58e4d-111">The interface represents a garbage collection task.</span></span>|  
|`TT_THREADPOOL_GATE`|<span data-ttu-id="58e4d-112">Die Schnittstelle stellt einen Gate-Thread-Task dar.</span><span class="sxs-lookup"><span data-stu-id="58e4d-112">The interface represents a gate thread task.</span></span>|  
|`TT_THREADPOOL_IOCOMPLETION`|<span data-ttu-id="58e4d-113">Die Schnittstelle stellt eine e/a-Thread-Aufgabe oder Thread eine Abschlussaufgabe-Port dar.</span><span class="sxs-lookup"><span data-stu-id="58e4d-113">The interface represents an I/O thread task or a completion port thread task.</span></span>|  
|`TT_THREADPOOL_TIMER`|<span data-ttu-id="58e4d-114">Die Schnittstelle stellt einen Timer-Thread-Task dar.</span><span class="sxs-lookup"><span data-stu-id="58e4d-114">The interface represents a timer thread task.</span></span>|  
|`TT_THREADPOOL_WAIT`|<span data-ttu-id="58e4d-115">Die Schnittstelle stellt einen warten-Thread-Task dar.</span><span class="sxs-lookup"><span data-stu-id="58e4d-115">The interface represents a wait thread task.</span></span>|  
|`TT_THREADPOOL_WORKER`|<span data-ttu-id="58e4d-116">Die Schnittstelle stellt einen Worker-Thread-Task dar.</span><span class="sxs-lookup"><span data-stu-id="58e4d-116">The interface represents a worker thread task.</span></span>|  
|`TT_UNKNOWN`|<span data-ttu-id="58e4d-117">Der Task ist unbekannt.</span><span class="sxs-lookup"><span data-stu-id="58e4d-117">The task is unknown.</span></span>|  
|`TT_USER`|<span data-ttu-id="58e4d-118">Die Schnittstelle stellt eine Benutzeraufgabe dar.</span><span class="sxs-lookup"><span data-stu-id="58e4d-118">The interface represents a user task.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="58e4d-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="58e4d-119">Requirements</span></span>  
 <span data-ttu-id="58e4d-120">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58e4d-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58e4d-121">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="58e4d-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="58e4d-122">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="58e4d-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="58e4d-123">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58e4d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58e4d-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58e4d-124">See Also</span></span>  
 [<span data-ttu-id="58e4d-125">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="58e4d-125">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
