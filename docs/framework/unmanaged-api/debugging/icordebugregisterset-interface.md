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
ms.openlocfilehash: 940810288b72be0d4dfc5366176663c22c369ebb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712377"
---
# <a name="icordebugregisterset-interface"></a><span data-ttu-id="25788-102">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="25788-102">ICorDebugRegisterSet Interface</span></span>

<span data-ttu-id="25788-103">Stellt den Satz der Register dar, die auf dem Computer verfügbar sind, der derzeit Code ausführt.</span><span class="sxs-lookup"><span data-stu-id="25788-103">Represents the set of registers available on the computer that is currently executing code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="25788-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="25788-104">Methods</span></span>  
  
|<span data-ttu-id="25788-105">Methode</span><span class="sxs-lookup"><span data-stu-id="25788-105">Method</span></span>|<span data-ttu-id="25788-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="25788-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="25788-107">GetRegisters-Methode</span><span class="sxs-lookup"><span data-stu-id="25788-107">GetRegisters Method</span></span>](icordebugregisterset-getregisters-method.md)|<span data-ttu-id="25788-108">Ruft den Wert der einzelnen Register (auf dem momentan ausgeführten Code) ab, der durch die Bitmaske angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="25788-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="25788-109">GetRegistersAvailable-Methode</span><span class="sxs-lookup"><span data-stu-id="25788-109">GetRegistersAvailable Method</span></span>](icordebugregisterset-getregistersavailable-method.md)|<span data-ttu-id="25788-110">Ruft eine Bitmaske ab, die angibt, welche Register in diesem `ICorDebugRegisterSet` aktuell verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="25788-110">Gets a bit mask indicating which registers in this `ICorDebugRegisterSet` are currently available.</span></span>|  
|[<span data-ttu-id="25788-111">GetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="25788-111">GetThreadContext Method</span></span>](icordebugregisterset-getthreadcontext-method.md)|<span data-ttu-id="25788-112">Ruft den Kontext des aktuellen Threads ab.</span><span class="sxs-lookup"><span data-stu-id="25788-112">Gets the context of the current thread.</span></span>|  
|[<span data-ttu-id="25788-113">SetRegisters-Methode</span><span class="sxs-lookup"><span data-stu-id="25788-113">SetRegisters Method</span></span>](icordebugregisterset-setregisters-method.md)|<span data-ttu-id="25788-114">Nicht implementiert für die .NET Framework Version 2,0.</span><span class="sxs-lookup"><span data-stu-id="25788-114">Not implemented for the .NET Framework version 2.0.</span></span>|  
|[<span data-ttu-id="25788-115">SetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="25788-115">SetThreadContext Method</span></span>](icordebugregisterset-setthreadcontext-method.md)|<span data-ttu-id="25788-116">Nicht implementiert für den .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="25788-116">Not implemented for the .NET Framework 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25788-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="25788-117">Remarks</span></span>  

 <span data-ttu-id="25788-118">Die `ICorDebugRegisterSet` -Schnittstelle unterstützt nur 32-Bit-Register.</span><span class="sxs-lookup"><span data-stu-id="25788-118">The `ICorDebugRegisterSet` interface supports only 32-bit registers.</span></span> <span data-ttu-id="25788-119">Verwenden Sie die [ICorDebugRegisterSet2](icordebugregisterset2-interface.md) -Schnittstelle auf Plattformen wie IA-64, die zusätzliche Register erfordern.</span><span class="sxs-lookup"><span data-stu-id="25788-119">Use the [ICorDebugRegisterSet2](icordebugregisterset2-interface.md) interface on platforms such as IA-64 that require additional registers.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="25788-120">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="25788-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25788-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="25788-121">Requirements</span></span>  

 <span data-ttu-id="25788-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25788-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25788-123">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="25788-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="25788-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25788-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25788-125">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25788-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25788-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="25788-126">See also</span></span>

- [<span data-ttu-id="25788-127">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="25788-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="25788-128">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="25788-128">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
