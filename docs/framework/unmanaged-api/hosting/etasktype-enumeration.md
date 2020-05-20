---
title: ETaskType-Enumeration
ms.date: 03/30/2017
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
ms.openlocfilehash: 435d23d4a56d6ea98e3d368f0a5aa37c73e31d96
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616163"
---
# <a name="etasktype-enumeration"></a><span data-ttu-id="111e2-102">ETaskType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="111e2-102">ETaskType Enumeration</span></span>
<span data-ttu-id="111e2-103">Enthält Werte, die den Typ der Aufgabe angeben, die durch eine [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) -oder [IHostTask](ihosttask-interface.md) -Schnittstelle dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="111e2-103">Contains values that indicate the type of task that is represented by either an [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) or an [IHostTask](ihosttask-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="111e2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="111e2-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="111e2-105">Member</span><span class="sxs-lookup"><span data-stu-id="111e2-105">Members</span></span>  
  
|<span data-ttu-id="111e2-106">Member</span><span class="sxs-lookup"><span data-stu-id="111e2-106">Member</span></span>|<span data-ttu-id="111e2-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="111e2-107">Description</span></span>|  
|------------|-----------------|  
|`TT_ADUNLOAD`|<span data-ttu-id="111e2-108">Die-Schnittstelle stellt eine Aufgabe zum Entladen einer Anwendungsdomäne dar.</span><span class="sxs-lookup"><span data-stu-id="111e2-108">The interface represents an application domain unloading task.</span></span>|  
|`TT_DEBUGGERHELPER`|<span data-ttu-id="111e2-109">Die-Schnittstelle stellt eine Debugger-hilfsaufgabe dar.</span><span class="sxs-lookup"><span data-stu-id="111e2-109">The interface represents a debugger helper task.</span></span>|  
|`TT_FINALIZER`|<span data-ttu-id="111e2-110">Die-Schnittstelle stellt eine Finalizer-Aufgabe dar.</span><span class="sxs-lookup"><span data-stu-id="111e2-110">The interface represents a finalizer task.</span></span>|  
|`TT_GC`|<span data-ttu-id="111e2-111">Die-Schnittstelle stellt eine Garbage Collection Aufgabe dar.</span><span class="sxs-lookup"><span data-stu-id="111e2-111">The interface represents a garbage collection task.</span></span>|  
|`TT_THREADPOOL_GATE`|<span data-ttu-id="111e2-112">Die-Schnittstelle stellt eine Gate-Thread Aufgabe dar.</span><span class="sxs-lookup"><span data-stu-id="111e2-112">The interface represents a gate thread task.</span></span>|  
|`TT_THREADPOOL_IOCOMPLETION`|<span data-ttu-id="111e2-113">Die-Schnittstelle stellt eine e/a-Thread Aufgabe oder einen Beendigungs Port-Thread Task dar.</span><span class="sxs-lookup"><span data-stu-id="111e2-113">The interface represents an I/O thread task or a completion port thread task.</span></span>|  
|`TT_THREADPOOL_TIMER`|<span data-ttu-id="111e2-114">Die-Schnittstelle stellt eine Zeit Geber Thread Aufgabe dar.</span><span class="sxs-lookup"><span data-stu-id="111e2-114">The interface represents a timer thread task.</span></span>|  
|`TT_THREADPOOL_WAIT`|<span data-ttu-id="111e2-115">Die-Schnittstelle stellt eine warte Thread Aufgabe dar.</span><span class="sxs-lookup"><span data-stu-id="111e2-115">The interface represents a wait thread task.</span></span>|  
|`TT_THREADPOOL_WORKER`|<span data-ttu-id="111e2-116">Die-Schnittstelle stellt eine Arbeits Thread Aufgabe dar.</span><span class="sxs-lookup"><span data-stu-id="111e2-116">The interface represents a worker thread task.</span></span>|  
|`TT_UNKNOWN`|<span data-ttu-id="111e2-117">Der Task ist unbekannt.</span><span class="sxs-lookup"><span data-stu-id="111e2-117">The task is unknown.</span></span>|  
|`TT_USER`|<span data-ttu-id="111e2-118">Die-Schnittstelle stellt eine Benutzer Aufgabe dar.</span><span class="sxs-lookup"><span data-stu-id="111e2-118">The interface represents a user task.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="111e2-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="111e2-119">Requirements</span></span>  
 <span data-ttu-id="111e2-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="111e2-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="111e2-121">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="111e2-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="111e2-122">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="111e2-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="111e2-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="111e2-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="111e2-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="111e2-124">See also</span></span>

- [<span data-ttu-id="111e2-125">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="111e2-125">Hosting Enumerations</span></span>](hosting-enumerations.md)
