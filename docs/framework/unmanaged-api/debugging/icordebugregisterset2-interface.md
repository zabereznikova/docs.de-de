---
title: ICorDebugRegisterSet2-Schnittstelle
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6f4947a9b6c0e3fd87ee474111f143d273c1d7b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422790"
---
# <a name="icordebugregisterset2-interface"></a><span data-ttu-id="2aff1-102">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2aff1-102">ICorDebugRegisterSet2 Interface</span></span>
<span data-ttu-id="2aff1-103">Erweitert die Funktionen von der [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) Schnittstelle für Hardwareplattformen, die mehr als 64 Registern.</span><span class="sxs-lookup"><span data-stu-id="2aff1-103">Extends the capabilities of the [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) interface for hardware platforms that have more than 64 registers.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2aff1-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="2aff1-104">Methods</span></span>  
  
|<span data-ttu-id="2aff1-105">Methode</span><span class="sxs-lookup"><span data-stu-id="2aff1-105">Method</span></span>|<span data-ttu-id="2aff1-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2aff1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2aff1-107">GetRegisters-Methode</span><span class="sxs-lookup"><span data-stu-id="2aff1-107">GetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-getregisters-method.md)|<span data-ttu-id="2aff1-108">Ruft den Wert jedes Register (auf dem Computer, der Code derzeit ausgeführt wird), die durch die Bitmaske angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2aff1-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="2aff1-109">GetRegistersAvailable-Methode</span><span class="sxs-lookup"><span data-stu-id="2aff1-109">GetRegistersAvailable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-getregistersavailable-method.md)|<span data-ttu-id="2aff1-110">Ruft ein Array von Bytes, die eine Bitmap mit den verfügbaren Registern bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="2aff1-110">Gets an array of bytes that provides a bitmap of the available registers.</span></span>|  
|[<span data-ttu-id="2aff1-111">SetRegisters-Methode</span><span class="sxs-lookup"><span data-stu-id="2aff1-111">SetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-setregisters-method.md)|<span data-ttu-id="2aff1-112">In .NET Framework, Version 2.0 implementiert nicht.</span><span class="sxs-lookup"><span data-stu-id="2aff1-112">Not implemented in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2aff1-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2aff1-113">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2aff1-114">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2aff1-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2aff1-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2aff1-115">Requirements</span></span>  
 <span data-ttu-id="2aff1-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2aff1-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2aff1-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2aff1-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2aff1-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2aff1-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2aff1-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2aff1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aff1-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2aff1-120">See Also</span></span>  
 [<span data-ttu-id="2aff1-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="2aff1-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="2aff1-122">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2aff1-122">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
