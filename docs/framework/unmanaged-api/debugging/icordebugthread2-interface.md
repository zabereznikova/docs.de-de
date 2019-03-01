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
ms.openlocfilehash: 0e162c114de013eed160a515dbc92fef47ea3327
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56980502"
---
# <a name="icordebugthread2-interface"></a><span data-ttu-id="421e9-102">ICorDebugThread2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="421e9-102">ICorDebugThread2 Interface</span></span>
<span data-ttu-id="421e9-103">Fungiert als logische Erweiterung von der ICorDebugThread-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="421e9-103">Serves as a logical extension to the ICorDebugThread interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="421e9-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="421e9-104">Methods</span></span>  
  
|<span data-ttu-id="421e9-105">Methode</span><span class="sxs-lookup"><span data-stu-id="421e9-105">Method</span></span>|<span data-ttu-id="421e9-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="421e9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="421e9-107">GetActiveFunctions-Methode</span><span class="sxs-lookup"><span data-stu-id="421e9-107">GetActiveFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md)|<span data-ttu-id="421e9-108">Ruft ein Array von COR_ACTIVE_FUNCTION-Instanzen, die Daten über die aktiven Funktionen in den Rahmen eines Threads enthalten.</span><span class="sxs-lookup"><span data-stu-id="421e9-108">Gets an array of COR_ACTIVE_FUNCTION instances that contain data about the active functions in a thread's frames.</span></span>|  
|[<span data-ttu-id="421e9-109">GetConnectionID-Methode</span><span class="sxs-lookup"><span data-stu-id="421e9-109">GetConnectionID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getconnectionid-method.md)|<span data-ttu-id="421e9-110">Ruft einen Verbindungsbezeichner für diese `ICorDebugThread2`.</span><span class="sxs-lookup"><span data-stu-id="421e9-110">Gets a connection identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="421e9-111">GetTaskID-Methode</span><span class="sxs-lookup"><span data-stu-id="421e9-111">GetTaskID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-gettaskid-method.md)|<span data-ttu-id="421e9-112">Ruft einen Aufgabenbezeichner für diese `ICorDebugThread2`.</span><span class="sxs-lookup"><span data-stu-id="421e9-112">Gets a task identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="421e9-113">GetVolatileOSThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="421e9-113">GetVolatileOSThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getvolatileosthreadid-method.md)|<span data-ttu-id="421e9-114">Ruft den Bezeichner des Threads für diese `ICorDebugThread2`.</span><span class="sxs-lookup"><span data-stu-id="421e9-114">Gets the operating system thread identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="421e9-115">InterceptCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="421e9-115">InterceptCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md)|<span data-ttu-id="421e9-116">Können Sie einen Debugger an die aktuelle Ausnahme in einem Thread abfangen.</span><span class="sxs-lookup"><span data-stu-id="421e9-116">Allows a debugger to intercept the current exception on a thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="421e9-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="421e9-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="421e9-118">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="421e9-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="421e9-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="421e9-119">Requirements</span></span>  
 <span data-ttu-id="421e9-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="421e9-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="421e9-121">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="421e9-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="421e9-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="421e9-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="421e9-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="421e9-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="421e9-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="421e9-124">See also</span></span>
- [<span data-ttu-id="421e9-125">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="421e9-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
