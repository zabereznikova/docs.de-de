---
title: ICorDebugRegisterSet2-Schnittstelle
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
- ICorDebugRegisterSet2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2
helpviewer_keywords:
- ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: d7fbccbf-3b6b-4db8-a96d-768e1cb6b1a6
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2f01a1d291216fca84b70fce8389efee3d7e2dd3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugregisterset2-interface"></a><span data-ttu-id="5e910-102">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e910-102">ICorDebugRegisterSet2 Interface</span></span>
<span data-ttu-id="5e910-103">Erweitert die Funktionen von der [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) Schnittstelle für Hardwareplattformen, die mehr als 64 Registern.</span><span class="sxs-lookup"><span data-stu-id="5e910-103">Extends the capabilities of the [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) interface for hardware platforms that have more than 64 registers.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5e910-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="5e910-104">Methods</span></span>  
  
|<span data-ttu-id="5e910-105">Methode</span><span class="sxs-lookup"><span data-stu-id="5e910-105">Method</span></span>|<span data-ttu-id="5e910-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5e910-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5e910-107">GetRegisters-Methode</span><span class="sxs-lookup"><span data-stu-id="5e910-107">GetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-getregisters-method.md)|<span data-ttu-id="5e910-108">Ruft den Wert jedes Register (auf dem Computer, der Code derzeit ausgeführt wird), die durch die Bitmaske angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5e910-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="5e910-109">GetRegistersAvailable-Methode</span><span class="sxs-lookup"><span data-stu-id="5e910-109">GetRegistersAvailable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-getregistersavailable-method.md)|<span data-ttu-id="5e910-110">Ruft ein Array von Bytes, die eine Bitmap mit den verfügbaren Registern bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="5e910-110">Gets an array of bytes that provides a bitmap of the available registers.</span></span>|  
|[<span data-ttu-id="5e910-111">SetRegisters-Methode</span><span class="sxs-lookup"><span data-stu-id="5e910-111">SetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-setregisters-method.md)|<span data-ttu-id="5e910-112">In .NET Framework, Version 2.0 implementiert nicht.</span><span class="sxs-lookup"><span data-stu-id="5e910-112">Not implemented in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e910-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5e910-113">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e910-114">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5e910-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e910-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5e910-115">Requirements</span></span>  
 <span data-ttu-id="5e910-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e910-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e910-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e910-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e910-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e910-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e910-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e910-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e910-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e910-120">See Also</span></span>  
 [<span data-ttu-id="5e910-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5e910-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="5e910-122">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e910-122">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
