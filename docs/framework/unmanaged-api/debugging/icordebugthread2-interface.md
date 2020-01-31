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
ms.openlocfilehash: fdaad46b739721ff95b712d4b6461a793ae0a480
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791429"
---
# <a name="icordebugthread2-interface"></a><span data-ttu-id="d5ef8-102">ICorDebugThread2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5ef8-102">ICorDebugThread2 Interface</span></span>
<span data-ttu-id="d5ef8-103">Dient als logische Erweiterung der ICorDebugThread-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d5ef8-103">Serves as a logical extension to the ICorDebugThread interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d5ef8-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="d5ef8-104">Methods</span></span>  
  
|<span data-ttu-id="d5ef8-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="d5ef8-105">Method</span></span>|<span data-ttu-id="d5ef8-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d5ef8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d5ef8-107">GetActiveFunctions-Methode</span><span class="sxs-lookup"><span data-stu-id="d5ef8-107">GetActiveFunctions Method</span></span>](icordebugthread2-getactivefunctions-method.md)|<span data-ttu-id="d5ef8-108">Ruft ein Array von COR_ACTIVE_FUNCTION-Instanzen ab, die Daten über die aktiven Funktionen in den Frames eines Threads enthalten.</span><span class="sxs-lookup"><span data-stu-id="d5ef8-108">Gets an array of COR_ACTIVE_FUNCTION instances that contain data about the active functions in a thread's frames.</span></span>|  
|[<span data-ttu-id="d5ef8-109">GetConnectionID-Methode</span><span class="sxs-lookup"><span data-stu-id="d5ef8-109">GetConnectionID Method</span></span>](icordebugthread2-getconnectionid-method.md)|<span data-ttu-id="d5ef8-110">Ruft einen Verbindungs Bezeichner für dieses `ICorDebugThread2`ab.</span><span class="sxs-lookup"><span data-stu-id="d5ef8-110">Gets a connection identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="d5ef8-111">GetTaskID-Methode</span><span class="sxs-lookup"><span data-stu-id="d5ef8-111">GetTaskID Method</span></span>](icordebugthread2-gettaskid-method.md)|<span data-ttu-id="d5ef8-112">Ruft einen Aufgaben Bezeichner für dieses `ICorDebugThread2`ab.</span><span class="sxs-lookup"><span data-stu-id="d5ef8-112">Gets a task identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="d5ef8-113">GetVolatileOSThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="d5ef8-113">GetVolatileOSThreadID Method</span></span>](icordebugthread2-getvolatileosthreadid-method.md)|<span data-ttu-id="d5ef8-114">Ruft den Thread Bezeichner des Betriebssystems für dieses `ICorDebugThread2`ab.</span><span class="sxs-lookup"><span data-stu-id="d5ef8-114">Gets the operating system thread identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="d5ef8-115">InterceptCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="d5ef8-115">InterceptCurrentException Method</span></span>](icordebugthread2-interceptcurrentexception-method.md)|<span data-ttu-id="d5ef8-116">Ermöglicht einem Debugger das Abfangen der aktuellen Ausnahme in einem Thread.</span><span class="sxs-lookup"><span data-stu-id="d5ef8-116">Allows a debugger to intercept the current exception on a thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5ef8-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d5ef8-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d5ef8-118">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d5ef8-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5ef8-119">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d5ef8-119">Requirements</span></span>  
 <span data-ttu-id="d5ef8-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5ef8-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5ef8-121">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d5ef8-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d5ef8-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5ef8-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5ef8-123">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5ef8-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5ef8-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5ef8-124">See also</span></span>

- [<span data-ttu-id="d5ef8-125">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d5ef8-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
