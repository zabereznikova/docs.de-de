---
title: ICorDebugRegisterSet2-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet2
helpviewer_keywords: ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: d7fbccbf-3b6b-4db8-a96d-768e1cb6b1a6
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 26967f50ded62f935a705c25eed58314b77bedd8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugregisterset2-interface"></a><span data-ttu-id="6aada-102">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6aada-102">ICorDebugRegisterSet2 Interface</span></span>
<span data-ttu-id="6aada-103">Erweitert die Funktionen von der [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) Schnittstelle für Hardwareplattformen, die mehr als 64 Registern.</span><span class="sxs-lookup"><span data-stu-id="6aada-103">Extends the capabilities of the [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) interface for hardware platforms that have more than 64 registers.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6aada-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="6aada-104">Methods</span></span>  
  
|<span data-ttu-id="6aada-105">Methode</span><span class="sxs-lookup"><span data-stu-id="6aada-105">Method</span></span>|<span data-ttu-id="6aada-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6aada-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6aada-107">GetRegisters-Methode</span><span class="sxs-lookup"><span data-stu-id="6aada-107">GetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-getregisters-method.md)|<span data-ttu-id="6aada-108">Ruft den Wert jedes Register (auf dem Computer, der Code derzeit ausgeführt wird), die durch die Bitmaske angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6aada-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="6aada-109">GetRegistersAvailable-Methode</span><span class="sxs-lookup"><span data-stu-id="6aada-109">GetRegistersAvailable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-getregistersavailable-method.md)|<span data-ttu-id="6aada-110">Ruft ein Array von Bytes, die eine Bitmap mit den verfügbaren Registern bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="6aada-110">Gets an array of bytes that provides a bitmap of the available registers.</span></span>|  
|[<span data-ttu-id="6aada-111">SetRegisters-Methode</span><span class="sxs-lookup"><span data-stu-id="6aada-111">SetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-setregisters-method.md)|<span data-ttu-id="6aada-112">In .NET Framework, Version 2.0 implementiert nicht.</span><span class="sxs-lookup"><span data-stu-id="6aada-112">Not implemented in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6aada-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6aada-113">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6aada-114">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="6aada-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6aada-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6aada-115">Requirements</span></span>  
 <span data-ttu-id="6aada-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6aada-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6aada-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6aada-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6aada-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6aada-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6aada-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6aada-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aada-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6aada-120">See Also</span></span>  
 [<span data-ttu-id="6aada-121">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="6aada-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="6aada-122">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6aada-122">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
