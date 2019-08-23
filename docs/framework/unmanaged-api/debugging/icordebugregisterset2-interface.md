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
ms.openlocfilehash: 95e8ad1ddce57252b7af3c7d72e8f8eb7bdb76b0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935088"
---
# <a name="icordebugregisterset2-interface"></a><span data-ttu-id="3ae0f-102">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3ae0f-102">ICorDebugRegisterSet2 Interface</span></span>
<span data-ttu-id="3ae0f-103">Erweitert die Funktionen der [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) -Schnittstelle für Hardwareplattformen mit mehr als 64 Registern.</span><span class="sxs-lookup"><span data-stu-id="3ae0f-103">Extends the capabilities of the [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) interface for hardware platforms that have more than 64 registers.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3ae0f-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="3ae0f-104">Methods</span></span>  
  
|<span data-ttu-id="3ae0f-105">Methode</span><span class="sxs-lookup"><span data-stu-id="3ae0f-105">Method</span></span>|<span data-ttu-id="3ae0f-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3ae0f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3ae0f-107">GetRegisters-Methode</span><span class="sxs-lookup"><span data-stu-id="3ae0f-107">GetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-getregisters-method.md)|<span data-ttu-id="3ae0f-108">Ruft den Wert der einzelnen Register (auf dem momentan ausgeführten Code) ab, der durch die Bitmaske angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="3ae0f-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="3ae0f-109">GetRegistersAvailable-Methode</span><span class="sxs-lookup"><span data-stu-id="3ae0f-109">GetRegistersAvailable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-getregistersavailable-method.md)|<span data-ttu-id="3ae0f-110">Ruft ein Bytearray ab, das eine Bitmap der verfügbaren Register bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="3ae0f-110">Gets an array of bytes that provides a bitmap of the available registers.</span></span>|  
|[<span data-ttu-id="3ae0f-111">SetRegisters-Methode</span><span class="sxs-lookup"><span data-stu-id="3ae0f-111">SetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-setregisters-method.md)|<span data-ttu-id="3ae0f-112">Nicht in der .NET Framework Version 2,0 implementiert.</span><span class="sxs-lookup"><span data-stu-id="3ae0f-112">Not implemented in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ae0f-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3ae0f-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3ae0f-114">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3ae0f-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ae0f-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3ae0f-115">Requirements</span></span>  
 <span data-ttu-id="3ae0f-116">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ae0f-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ae0f-117">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="3ae0f-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3ae0f-118">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ae0f-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ae0f-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ae0f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ae0f-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ae0f-120">See also</span></span>

- [<span data-ttu-id="3ae0f-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="3ae0f-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="3ae0f-122">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3ae0f-122">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
