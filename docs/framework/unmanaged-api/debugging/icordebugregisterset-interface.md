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
ms.openlocfilehash: f435db28d5c85d576f69e7612841fc46ae142332
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792073"
---
# <a name="icordebugregisterset-interface"></a><span data-ttu-id="cdfa5-102">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cdfa5-102">ICorDebugRegisterSet Interface</span></span>
<span data-ttu-id="cdfa5-103">Stellt den Satz der Register dar, die auf dem Computer verfügbar sind, der derzeit Code ausführt.</span><span class="sxs-lookup"><span data-stu-id="cdfa5-103">Represents the set of registers available on the computer that is currently executing code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cdfa5-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="cdfa5-104">Methods</span></span>  
  
|<span data-ttu-id="cdfa5-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="cdfa5-105">Method</span></span>|<span data-ttu-id="cdfa5-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cdfa5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cdfa5-107">GetRegisters-Methode</span><span class="sxs-lookup"><span data-stu-id="cdfa5-107">GetRegisters Method</span></span>](icordebugregisterset-getregisters-method.md)|<span data-ttu-id="cdfa5-108">Ruft den Wert der einzelnen Register (auf dem momentan ausgeführten Code) ab, der durch die Bitmaske angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="cdfa5-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="cdfa5-109">GetRegistersAvailable-Methode</span><span class="sxs-lookup"><span data-stu-id="cdfa5-109">GetRegistersAvailable Method</span></span>](icordebugregisterset-getregistersavailable-method.md)|<span data-ttu-id="cdfa5-110">Ruft eine Bitmaske ab, die angibt, welche Register in diesem `ICorDebugRegisterSet` derzeit verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="cdfa5-110">Gets a bit mask indicating which registers in this `ICorDebugRegisterSet` are currently available.</span></span>|  
|[<span data-ttu-id="cdfa5-111">GetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="cdfa5-111">GetThreadContext Method</span></span>](icordebugregisterset-getthreadcontext-method.md)|<span data-ttu-id="cdfa5-112">Ruft den Kontext des aktuellen Threads ab.</span><span class="sxs-lookup"><span data-stu-id="cdfa5-112">Gets the context of the current thread.</span></span>|  
|[<span data-ttu-id="cdfa5-113">SetRegisters-Methode</span><span class="sxs-lookup"><span data-stu-id="cdfa5-113">SetRegisters Method</span></span>](icordebugregisterset-setregisters-method.md)|<span data-ttu-id="cdfa5-114">Nicht implementiert für die .NET Framework Version 2,0.</span><span class="sxs-lookup"><span data-stu-id="cdfa5-114">Not implemented for the .NET Framework version 2.0.</span></span>|  
|[<span data-ttu-id="cdfa5-115">SetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="cdfa5-115">SetThreadContext Method</span></span>](icordebugregisterset-setthreadcontext-method.md)|<span data-ttu-id="cdfa5-116">Nicht implementiert für den .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="cdfa5-116">Not implemented for the .NET Framework 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cdfa5-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cdfa5-117">Remarks</span></span>  
 <span data-ttu-id="cdfa5-118">Die `ICorDebugRegisterSet`-Schnittstelle unterstützt nur 32-Bit-Register.</span><span class="sxs-lookup"><span data-stu-id="cdfa5-118">The `ICorDebugRegisterSet` interface supports only 32-bit registers.</span></span> <span data-ttu-id="cdfa5-119">Verwenden Sie die [ICorDebugRegisterSet2](icordebugregisterset2-interface.md) -Schnittstelle auf Plattformen wie IA-64, die zusätzliche Register erfordern.</span><span class="sxs-lookup"><span data-stu-id="cdfa5-119">Use the [ICorDebugRegisterSet2](icordebugregisterset2-interface.md) interface on platforms such as IA-64 that require additional registers.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cdfa5-120">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="cdfa5-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdfa5-121">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cdfa5-121">Requirements</span></span>  
 <span data-ttu-id="cdfa5-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cdfa5-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdfa5-123">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cdfa5-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cdfa5-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cdfa5-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cdfa5-125">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdfa5-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdfa5-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cdfa5-126">See also</span></span>

- [<span data-ttu-id="cdfa5-127">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="cdfa5-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="cdfa5-128">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cdfa5-128">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
