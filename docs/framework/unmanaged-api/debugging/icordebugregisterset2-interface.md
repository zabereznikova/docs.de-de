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
ms.openlocfilehash: c04bb3a7584fcb783af929e87713dbec67ad705f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712319"
---
# <a name="icordebugregisterset2-interface"></a><span data-ttu-id="f8c61-102">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8c61-102">ICorDebugRegisterSet2 Interface</span></span>

<span data-ttu-id="f8c61-103">Erweitert die Funktionen der [ICorDebugRegisterSet](icordebugregisterset-interface.md) -Schnittstelle für Hardwareplattformen mit mehr als 64 Registern.</span><span class="sxs-lookup"><span data-stu-id="f8c61-103">Extends the capabilities of the [ICorDebugRegisterSet](icordebugregisterset-interface.md) interface for hardware platforms that have more than 64 registers.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f8c61-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="f8c61-104">Methods</span></span>  
  
|<span data-ttu-id="f8c61-105">Methode</span><span class="sxs-lookup"><span data-stu-id="f8c61-105">Method</span></span>|<span data-ttu-id="f8c61-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f8c61-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f8c61-107">GetRegisters-Methode</span><span class="sxs-lookup"><span data-stu-id="f8c61-107">GetRegisters Method</span></span>](icordebugregisterset2-getregisters-method.md)|<span data-ttu-id="f8c61-108">Ruft den Wert der einzelnen Register (auf dem momentan ausgeführten Code) ab, der durch die Bitmaske angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f8c61-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="f8c61-109">GetRegistersAvailable-Methode</span><span class="sxs-lookup"><span data-stu-id="f8c61-109">GetRegistersAvailable Method</span></span>](icordebugregisterset2-getregistersavailable-method.md)|<span data-ttu-id="f8c61-110">Ruft ein Bytearray ab, das eine Bitmap der verfügbaren Register bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="f8c61-110">Gets an array of bytes that provides a bitmap of the available registers.</span></span>|  
|[<span data-ttu-id="f8c61-111">SetRegisters-Methode</span><span class="sxs-lookup"><span data-stu-id="f8c61-111">SetRegisters Method</span></span>](icordebugregisterset2-setregisters-method.md)|<span data-ttu-id="f8c61-112">Nicht in der .NET Framework Version 2,0 implementiert.</span><span class="sxs-lookup"><span data-stu-id="f8c61-112">Not implemented in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8c61-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f8c61-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f8c61-114">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f8c61-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8c61-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f8c61-115">Requirements</span></span>  

 <span data-ttu-id="f8c61-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8c61-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8c61-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f8c61-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f8c61-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8c61-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8c61-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8c61-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8c61-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f8c61-120">See also</span></span>

- [<span data-ttu-id="f8c61-121">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f8c61-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f8c61-122">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8c61-122">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
