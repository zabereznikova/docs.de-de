---
title: ICorDebugThread2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugThread2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2
helpviewer_keywords:
- ICorDebugThread2 interface [.NET Framework debugging]
ms.assetid: 678f89f9-cce7-46d1-af87-5e989abaa93c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4d21c221bba3ac668924003f96580bb660229ad7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963006"
---
# <a name="icordebugthread2-interface"></a><span data-ttu-id="c68d6-102">ICorDebugThread2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c68d6-102">ICorDebugThread2 Interface</span></span>
<span data-ttu-id="c68d6-103">Dient als logische Erweiterung der ICorDebugThread-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c68d6-103">Serves as a logical extension to the ICorDebugThread interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c68d6-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="c68d6-104">Methods</span></span>  
  
|<span data-ttu-id="c68d6-105">Methode</span><span class="sxs-lookup"><span data-stu-id="c68d6-105">Method</span></span>|<span data-ttu-id="c68d6-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c68d6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c68d6-107">GetActiveFunctions-Methode</span><span class="sxs-lookup"><span data-stu-id="c68d6-107">GetActiveFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md)|<span data-ttu-id="c68d6-108">Ruft ein Array von COR_ACTIVE_FUNCTION-Instanzen ab, die Daten über die aktiven Funktionen in den Frames eines Threads enthalten.</span><span class="sxs-lookup"><span data-stu-id="c68d6-108">Gets an array of COR_ACTIVE_FUNCTION instances that contain data about the active functions in a thread's frames.</span></span>|  
|[<span data-ttu-id="c68d6-109">GetConnectionID-Methode</span><span class="sxs-lookup"><span data-stu-id="c68d6-109">GetConnectionID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getconnectionid-method.md)|<span data-ttu-id="c68d6-110">Ruft einen Verbindungs Bezeichner für `ICorDebugThread2`dieses ab.</span><span class="sxs-lookup"><span data-stu-id="c68d6-110">Gets a connection identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="c68d6-111">GetTaskID-Methode</span><span class="sxs-lookup"><span data-stu-id="c68d6-111">GetTaskID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-gettaskid-method.md)|<span data-ttu-id="c68d6-112">Ruft einen Aufgaben Bezeichner für `ICorDebugThread2`dieses ab.</span><span class="sxs-lookup"><span data-stu-id="c68d6-112">Gets a task identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="c68d6-113">GetVolatileOSThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="c68d6-113">GetVolatileOSThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getvolatileosthreadid-method.md)|<span data-ttu-id="c68d6-114">Ruft den Thread Bezeichner des Betriebssystems `ICorDebugThread2`für diesen ab.</span><span class="sxs-lookup"><span data-stu-id="c68d6-114">Gets the operating system thread identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="c68d6-115">InterceptCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="c68d6-115">InterceptCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md)|<span data-ttu-id="c68d6-116">Ermöglicht einem Debugger das Abfangen der aktuellen Ausnahme in einem Thread.</span><span class="sxs-lookup"><span data-stu-id="c68d6-116">Allows a debugger to intercept the current exception on a thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c68d6-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c68d6-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c68d6-118">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c68d6-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c68d6-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c68d6-119">Requirements</span></span>  
 <span data-ttu-id="c68d6-120">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c68d6-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c68d6-121">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="c68d6-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c68d6-122">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c68d6-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c68d6-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c68d6-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c68d6-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c68d6-124">See also</span></span>

- [<span data-ttu-id="c68d6-125">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c68d6-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
