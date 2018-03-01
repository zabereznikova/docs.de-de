---
title: ICorDebugThread2 Schnittstelle1
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 907ba524164b1e0d167f7a88250c7d32910504f4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread2-interface1"></a><span data-ttu-id="55918-102">ICorDebugThread2 Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="55918-102">ICorDebugThread2 Interface1</span></span>
<span data-ttu-id="55918-103">Fungiert als logische Erweiterung von ICorDebugThread-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="55918-103">Serves as a logical extension to the ICorDebugThread interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="55918-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="55918-104">Methods</span></span>  
  
|<span data-ttu-id="55918-105">Methode</span><span class="sxs-lookup"><span data-stu-id="55918-105">Method</span></span>|<span data-ttu-id="55918-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="55918-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="55918-107">GetActiveFunctions-Methode</span><span class="sxs-lookup"><span data-stu-id="55918-107">GetActiveFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md)|<span data-ttu-id="55918-108">Ruft ein Array von COR_ACTIVE_FUNCTION-Instanzen, die Daten über die aktiven Funktionen im Rahmen eines Threads enthalten.</span><span class="sxs-lookup"><span data-stu-id="55918-108">Gets an array of COR_ACTIVE_FUNCTION instances that contain data about the active functions in a thread's frames.</span></span>|  
|[<span data-ttu-id="55918-109">GetConnectionID-Methode</span><span class="sxs-lookup"><span data-stu-id="55918-109">GetConnectionID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getconnectionid-method.md)|<span data-ttu-id="55918-110">Ruft einen Verbindungsbezeichner für `ICorDebugThread2`.</span><span class="sxs-lookup"><span data-stu-id="55918-110">Gets a connection identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="55918-111">GetTaskID-Methode</span><span class="sxs-lookup"><span data-stu-id="55918-111">GetTaskID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-gettaskid-method.md)|<span data-ttu-id="55918-112">Ruft einen Aufgabenbezeichner für `ICorDebugThread2`.</span><span class="sxs-lookup"><span data-stu-id="55918-112">Gets a task identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="55918-113">GetVolatileOSThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="55918-113">GetVolatileOSThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getvolatileosthreadid-method.md)|<span data-ttu-id="55918-114">Ruft den Threadbezeichner des Betriebssystems für `ICorDebugThread2`.</span><span class="sxs-lookup"><span data-stu-id="55918-114">Gets the operating system thread identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="55918-115">InterceptCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="55918-115">InterceptCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md)|<span data-ttu-id="55918-116">Einen Debugger ermöglicht, die aktuelle Ausnahme in einem Thread abfangen.</span><span class="sxs-lookup"><span data-stu-id="55918-116">Allows a debugger to intercept the current exception on a thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55918-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="55918-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="55918-118">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="55918-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55918-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="55918-119">Requirements</span></span>  
 <span data-ttu-id="55918-120">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55918-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55918-121">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="55918-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="55918-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55918-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55918-123">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55918-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55918-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55918-124">See Also</span></span>  
 [<span data-ttu-id="55918-125">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="55918-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
