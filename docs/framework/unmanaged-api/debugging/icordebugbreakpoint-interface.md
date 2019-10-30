---
title: ICorDebugBreakpoint-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint
helpviewer_keywords:
- ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: aa5ad3d7-e1bb-42af-99bc-471224e3bcaa
topic_type:
- apiref
ms.openlocfilehash: 29bb84341c2cb4177c43f798d25a1a6d50099aa5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122796"
---
# <a name="icordebugbreakpoint-interface"></a><span data-ttu-id="e7488-102">ICorDebugBreakpoint-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e7488-102">ICorDebugBreakpoint Interface</span></span>

<span data-ttu-id="e7488-103">Stellt einen Haltepunkt in einer Funktion oder einen Überwachungs Punkt auf einem Wert dar.</span><span class="sxs-lookup"><span data-stu-id="e7488-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e7488-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="e7488-104">Methods</span></span>  
  
|<span data-ttu-id="e7488-105">Methode</span><span class="sxs-lookup"><span data-stu-id="e7488-105">Method</span></span>|<span data-ttu-id="e7488-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e7488-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e7488-107">Activate-Methode</span><span class="sxs-lookup"><span data-stu-id="e7488-107">Activate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|<span data-ttu-id="e7488-108">Legt den aktiven Zustand dieses `ICorDebugBreakpoint`fest.</span><span class="sxs-lookup"><span data-stu-id="e7488-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="e7488-109">IsActive-Methode</span><span class="sxs-lookup"><span data-stu-id="e7488-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="e7488-110">Ruft einen Wert ab, der angibt, ob dieses `ICorDebugBreakpoint` aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="e7488-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7488-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e7488-111">Remarks</span></span>  
 <span data-ttu-id="e7488-112">Haltepunkte unterstützen bedingte Ausdrücke nicht direkt.</span><span class="sxs-lookup"><span data-stu-id="e7488-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="e7488-113">Wenn eine solche Funktionalität gewünscht ist, muss Sie von einem Debugger zusätzlich zu `ICorDebugBreakpoint`implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="e7488-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="e7488-114">Die ICorDebugFunctionBreakpoint-Schnittstelle erweitert `ICorDebugBreakpoint`, um Breakpoints innerhalb von Funktionen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e7488-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e7488-115">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e7488-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7488-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e7488-116">Requirements</span></span>  
 <span data-ttu-id="e7488-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7488-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7488-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e7488-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e7488-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7488-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7488-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7488-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7488-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7488-121">See also</span></span>

- [<span data-ttu-id="e7488-122">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e7488-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
