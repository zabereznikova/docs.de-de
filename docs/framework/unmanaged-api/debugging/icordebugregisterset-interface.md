---
title: ICorDebugRegisterSet-Schnittstelle
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
- ICorDebugRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet
helpviewer_keywords:
- ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: d3d9676d-0b87-4bc3-b679-7bbc7a186c88
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 714f3d7839ce1d8b65405b6cb3c91d43f1db6642
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugregisterset-interface"></a><span data-ttu-id="62549-102">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="62549-102">ICorDebugRegisterSet Interface</span></span>
<span data-ttu-id="62549-103">Stellt den Satz von Registern zur Verfügung, auf dem Computer, der Code derzeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="62549-103">Represents the set of registers available on the computer that is currently executing code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="62549-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="62549-104">Methods</span></span>  
  
|<span data-ttu-id="62549-105">Methode</span><span class="sxs-lookup"><span data-stu-id="62549-105">Method</span></span>|<span data-ttu-id="62549-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62549-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="62549-107">GetRegisters-Methode</span><span class="sxs-lookup"><span data-stu-id="62549-107">GetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md)|<span data-ttu-id="62549-108">Ruft den Wert jedes Register (auf dem Computer, der Code derzeit ausgeführt wird), die durch die Bitmaske angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="62549-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="62549-109">GetRegistersAvailable-Methode</span><span class="sxs-lookup"><span data-stu-id="62549-109">GetRegistersAvailable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)|<span data-ttu-id="62549-110">Ruft eine Bitmaske, die angibt, welche Register in diesem `ICorDebugRegisterSet` sind derzeit verfügbar.</span><span class="sxs-lookup"><span data-stu-id="62549-110">Gets a bit mask indicating which registers in this `ICorDebugRegisterSet` are currently available.</span></span>|  
|[<span data-ttu-id="62549-111">GetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="62549-111">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getthreadcontext-method.md)|<span data-ttu-id="62549-112">Ruft den Kontext des aktuellen Threads ab.</span><span class="sxs-lookup"><span data-stu-id="62549-112">Gets the context of the current thread.</span></span>|  
|[<span data-ttu-id="62549-113">SetRegisters-Methode</span><span class="sxs-lookup"><span data-stu-id="62549-113">SetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setregisters-method.md)|<span data-ttu-id="62549-114">Für .NET Framework, Version 2.0 implementiert nicht.</span><span class="sxs-lookup"><span data-stu-id="62549-114">Not implemented for the .NET Framework version 2.0.</span></span>|  
|[<span data-ttu-id="62549-115">SetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="62549-115">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setthreadcontext-method.md)|<span data-ttu-id="62549-116">Für .NET Framework 2.0 implementiert nicht.</span><span class="sxs-lookup"><span data-stu-id="62549-116">Not implemented for the .NET Framework 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62549-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="62549-117">Remarks</span></span>  
 <span data-ttu-id="62549-118">Die `ICorDebugRegisterSet` -Schnittstelle unterstützt nur 32-Bit-Register.</span><span class="sxs-lookup"><span data-stu-id="62549-118">The `ICorDebugRegisterSet` interface supports only 32-bit registers.</span></span> <span data-ttu-id="62549-119">Verwenden der [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) Schnittstelle auf Plattformen wie IA-64, die zusätzliche Register erfordern.</span><span class="sxs-lookup"><span data-stu-id="62549-119">Use the [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) interface on platforms such as IA-64 that require additional registers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="62549-120">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="62549-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62549-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="62549-121">Requirements</span></span>  
 <span data-ttu-id="62549-122">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62549-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62549-123">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="62549-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62549-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62549-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62549-125">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62549-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62549-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62549-126">See Also</span></span>  
 [<span data-ttu-id="62549-127">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="62549-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="62549-128">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="62549-128">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
