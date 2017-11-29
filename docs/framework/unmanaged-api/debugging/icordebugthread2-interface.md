---
title: ICorDebugThread2 Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread2
helpviewer_keywords: ICorDebugThread2 interface [.NET Framework debugging]
ms.assetid: 678f89f9-cce7-46d1-af87-5e989abaa93c
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5d3a554d075adb56294e4693b234ce22735fb982
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthread2-interface1"></a><span data-ttu-id="911bd-102">ICorDebugThread2 Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="911bd-102">ICorDebugThread2 Interface1</span></span>
<span data-ttu-id="911bd-103">Fungiert als logische Erweiterung von ICorDebugThread-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="911bd-103">Serves as a logical extension to the ICorDebugThread interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="911bd-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="911bd-104">Methods</span></span>  
  
|<span data-ttu-id="911bd-105">Methode</span><span class="sxs-lookup"><span data-stu-id="911bd-105">Method</span></span>|<span data-ttu-id="911bd-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="911bd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="911bd-107">GetActiveFunctions-Methode</span><span class="sxs-lookup"><span data-stu-id="911bd-107">GetActiveFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md)|<span data-ttu-id="911bd-108">Ruft ein Array von COR_ACTIVE_FUNCTION-Instanzen, die Daten über die aktiven Funktionen im Rahmen eines Threads enthalten.</span><span class="sxs-lookup"><span data-stu-id="911bd-108">Gets an array of COR_ACTIVE_FUNCTION instances that contain data about the active functions in a thread's frames.</span></span>|  
|[<span data-ttu-id="911bd-109">GetConnectionID-Methode</span><span class="sxs-lookup"><span data-stu-id="911bd-109">GetConnectionID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getconnectionid-method.md)|<span data-ttu-id="911bd-110">Ruft einen Verbindungsbezeichner für `ICorDebugThread2`.</span><span class="sxs-lookup"><span data-stu-id="911bd-110">Gets a connection identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="911bd-111">GetTaskID-Methode</span><span class="sxs-lookup"><span data-stu-id="911bd-111">GetTaskID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-gettaskid-method.md)|<span data-ttu-id="911bd-112">Ruft einen Aufgabenbezeichner für `ICorDebugThread2`.</span><span class="sxs-lookup"><span data-stu-id="911bd-112">Gets a task identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="911bd-113">GetVolatileOSThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="911bd-113">GetVolatileOSThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getvolatileosthreadid-method.md)|<span data-ttu-id="911bd-114">Ruft den Threadbezeichner des Betriebssystems für `ICorDebugThread2`.</span><span class="sxs-lookup"><span data-stu-id="911bd-114">Gets the operating system thread identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="911bd-115">InterceptCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="911bd-115">InterceptCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md)|<span data-ttu-id="911bd-116">Einen Debugger ermöglicht, die aktuelle Ausnahme in einem Thread abfangen.</span><span class="sxs-lookup"><span data-stu-id="911bd-116">Allows a debugger to intercept the current exception on a thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="911bd-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="911bd-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="911bd-118">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="911bd-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="911bd-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="911bd-119">Requirements</span></span>  
 <span data-ttu-id="911bd-120">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="911bd-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="911bd-121">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="911bd-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="911bd-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="911bd-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="911bd-123">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="911bd-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="911bd-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="911bd-124">See Also</span></span>  
 [<span data-ttu-id="911bd-125">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="911bd-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
