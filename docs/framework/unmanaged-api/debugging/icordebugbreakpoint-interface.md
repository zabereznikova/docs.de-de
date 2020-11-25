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
ms.openlocfilehash: 0c84a91c7da553d0c84a4995b4744576d861dcb9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730200"
---
# <a name="icordebugbreakpoint-interface"></a><span data-ttu-id="254a6-102">ICorDebugBreakpoint-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="254a6-102">ICorDebugBreakpoint Interface</span></span>

<span data-ttu-id="254a6-103">Stellt einen Haltepunkt in einer Funktion oder einen Überwachungs Punkt auf einem Wert dar.</span><span class="sxs-lookup"><span data-stu-id="254a6-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="254a6-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="254a6-104">Methods</span></span>  
  
|<span data-ttu-id="254a6-105">Methode</span><span class="sxs-lookup"><span data-stu-id="254a6-105">Method</span></span>|<span data-ttu-id="254a6-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="254a6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="254a6-107">Activate-Methode</span><span class="sxs-lookup"><span data-stu-id="254a6-107">Activate Method</span></span>](icordebugbreakpoint-activate-method.md)|<span data-ttu-id="254a6-108">Legt den aktiven Zustand dieses fest `ICorDebugBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="254a6-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="254a6-109">IsActive-Methode</span><span class="sxs-lookup"><span data-stu-id="254a6-109">IsActive Method</span></span>](icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="254a6-110">Ruft einen Wert ab, der angibt, ob diese `ICorDebugBreakpoint` aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="254a6-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="254a6-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="254a6-111">Remarks</span></span>  

 <span data-ttu-id="254a6-112">Haltepunkte unterstützen bedingte Ausdrücke nicht direkt.</span><span class="sxs-lookup"><span data-stu-id="254a6-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="254a6-113">Wenn eine solche Funktionalität gewünscht ist, muss Sie von einem Debugger zusätzlich zu implementiert werden `ICorDebugBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="254a6-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="254a6-114">Die ICorDebugFunctionBreakpoint-Schnittstelle erweitert `ICorDebugBreakpoint` , um Breakpoints innerhalb von Funktionen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="254a6-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="254a6-115">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="254a6-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="254a6-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="254a6-116">Requirements</span></span>  

 <span data-ttu-id="254a6-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="254a6-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="254a6-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="254a6-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="254a6-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="254a6-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="254a6-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="254a6-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="254a6-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="254a6-121">See also</span></span>

- [<span data-ttu-id="254a6-122">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="254a6-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
