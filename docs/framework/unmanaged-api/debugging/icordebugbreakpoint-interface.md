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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a7e454c15ddfa977a6d06921a5d80a6c05dca92f
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973573"
---
# <a name="icordebugbreakpoint-interface"></a><span data-ttu-id="9753c-102">ICorDebugBreakpoint-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9753c-102">ICorDebugBreakpoint Interface</span></span>

<span data-ttu-id="9753c-103">Stellt einen Haltepunkt in einer Funktion oder einen Beobachtungspunkt für einen Wert dar.</span><span class="sxs-lookup"><span data-stu-id="9753c-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9753c-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="9753c-104">Methods</span></span>  
  
|<span data-ttu-id="9753c-105">Methode</span><span class="sxs-lookup"><span data-stu-id="9753c-105">Method</span></span>|<span data-ttu-id="9753c-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9753c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9753c-107">Activate-Methode</span><span class="sxs-lookup"><span data-stu-id="9753c-107">Activate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|<span data-ttu-id="9753c-108">Legt den aktiven Zustand dieses `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="9753c-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="9753c-109">IsActive-Methode</span><span class="sxs-lookup"><span data-stu-id="9753c-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="9753c-110">Ruft einen Wert, der angibt, ob dies `ICorDebugBreakpoint` aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="9753c-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9753c-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9753c-111">Remarks</span></span>  
 <span data-ttu-id="9753c-112">Haltepunkte unterstützen die bedingte Ausdrücke nicht direkt.</span><span class="sxs-lookup"><span data-stu-id="9753c-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="9753c-113">Wenn eine solche Funktionalität gewünscht ist, muss ein Debugger implementieren oberhalb des `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="9753c-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="9753c-114">ICorDebugFunctionBreakpoint-Schnittstelle erweitert `ICorDebugBreakpoint` um Haltepunkte innerhalb von Funktionen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="9753c-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9753c-115">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9753c-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9753c-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9753c-116">Requirements</span></span>  
 <span data-ttu-id="9753c-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9753c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9753c-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9753c-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9753c-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9753c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9753c-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9753c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9753c-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9753c-121">See also</span></span>
- [<span data-ttu-id="9753c-122">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9753c-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
