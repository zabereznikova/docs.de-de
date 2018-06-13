---
title: ICorDebugRegisterSet-Schnittstelle
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c4b28d60b3a1da32d2d9db84aa92ca4c9bf769aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423194"
---
# <a name="icordebugregisterset-interface"></a><span data-ttu-id="2d2a8-102">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2d2a8-102">ICorDebugRegisterSet Interface</span></span>
<span data-ttu-id="2d2a8-103">Stellt den Satz von Registern zur Verfügung, auf dem Computer, der Code derzeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2d2a8-103">Represents the set of registers available on the computer that is currently executing code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2d2a8-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="2d2a8-104">Methods</span></span>  
  
|<span data-ttu-id="2d2a8-105">Methode</span><span class="sxs-lookup"><span data-stu-id="2d2a8-105">Method</span></span>|<span data-ttu-id="2d2a8-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2d2a8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2d2a8-107">GetRegisters-Methode</span><span class="sxs-lookup"><span data-stu-id="2d2a8-107">GetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md)|<span data-ttu-id="2d2a8-108">Ruft den Wert jedes Register (auf dem Computer, der Code derzeit ausgeführt wird), die durch die Bitmaske angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2d2a8-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="2d2a8-109">GetRegistersAvailable-Methode</span><span class="sxs-lookup"><span data-stu-id="2d2a8-109">GetRegistersAvailable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)|<span data-ttu-id="2d2a8-110">Ruft eine Bitmaske, die angibt, welche Register in diesem `ICorDebugRegisterSet` sind derzeit verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2d2a8-110">Gets a bit mask indicating which registers in this `ICorDebugRegisterSet` are currently available.</span></span>|  
|[<span data-ttu-id="2d2a8-111">GetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="2d2a8-111">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getthreadcontext-method.md)|<span data-ttu-id="2d2a8-112">Ruft den Kontext des aktuellen Threads ab.</span><span class="sxs-lookup"><span data-stu-id="2d2a8-112">Gets the context of the current thread.</span></span>|  
|[<span data-ttu-id="2d2a8-113">SetRegisters-Methode</span><span class="sxs-lookup"><span data-stu-id="2d2a8-113">SetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setregisters-method.md)|<span data-ttu-id="2d2a8-114">Für .NET Framework, Version 2.0 implementiert nicht.</span><span class="sxs-lookup"><span data-stu-id="2d2a8-114">Not implemented for the .NET Framework version 2.0.</span></span>|  
|[<span data-ttu-id="2d2a8-115">SetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="2d2a8-115">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setthreadcontext-method.md)|<span data-ttu-id="2d2a8-116">Für .NET Framework 2.0 implementiert nicht.</span><span class="sxs-lookup"><span data-stu-id="2d2a8-116">Not implemented for the .NET Framework 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d2a8-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2d2a8-117">Remarks</span></span>  
 <span data-ttu-id="2d2a8-118">Die `ICorDebugRegisterSet` -Schnittstelle unterstützt nur 32-Bit-Register.</span><span class="sxs-lookup"><span data-stu-id="2d2a8-118">The `ICorDebugRegisterSet` interface supports only 32-bit registers.</span></span> <span data-ttu-id="2d2a8-119">Verwenden der [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) Schnittstelle auf Plattformen wie IA-64, die zusätzliche Register erfordern.</span><span class="sxs-lookup"><span data-stu-id="2d2a8-119">Use the [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) interface on platforms such as IA-64 that require additional registers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2d2a8-120">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2d2a8-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d2a8-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2d2a8-121">Requirements</span></span>  
 <span data-ttu-id="2d2a8-122">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d2a8-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d2a8-123">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2d2a8-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2d2a8-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d2a8-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d2a8-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d2a8-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d2a8-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d2a8-126">See Also</span></span>  
 [<span data-ttu-id="2d2a8-127">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="2d2a8-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="2d2a8-128">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2d2a8-128">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
