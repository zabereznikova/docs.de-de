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
ms.openlocfilehash: 608c2cea79c20a43d65fcbf37ba13242fa465100
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969312"
---
# <a name="icordebugbreakpoint-interface"></a><span data-ttu-id="09c39-102">ICorDebugBreakpoint-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="09c39-102">ICorDebugBreakpoint Interface</span></span>

<span data-ttu-id="09c39-103">Stellt einen Haltepunkt in einer Funktion oder einen Überwachungs Punkt auf einem Wert dar.</span><span class="sxs-lookup"><span data-stu-id="09c39-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="09c39-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="09c39-104">Methods</span></span>  
  
|<span data-ttu-id="09c39-105">Methode</span><span class="sxs-lookup"><span data-stu-id="09c39-105">Method</span></span>|<span data-ttu-id="09c39-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="09c39-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="09c39-107">Activate-Methode</span><span class="sxs-lookup"><span data-stu-id="09c39-107">Activate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|<span data-ttu-id="09c39-108">Legt den aktiven Zustand dieses `ICorDebugBreakpoint`fest.</span><span class="sxs-lookup"><span data-stu-id="09c39-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="09c39-109">IsActive-Methode</span><span class="sxs-lookup"><span data-stu-id="09c39-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="09c39-110">Ruft einen Wert ab, der angibt `ICorDebugBreakpoint` , ob diese aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="09c39-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09c39-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="09c39-111">Remarks</span></span>  
 <span data-ttu-id="09c39-112">Haltepunkte unterstützen bedingte Ausdrücke nicht direkt.</span><span class="sxs-lookup"><span data-stu-id="09c39-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="09c39-113">Wenn eine solche Funktionalität gewünscht ist, muss Sie von `ICorDebugBreakpoint`einem Debugger zusätzlich zu implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="09c39-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="09c39-114">Die ICorDebugFunctionBreakpoint-Schnitt `ICorDebugBreakpoint` Stelle erweitert, um Breakpoints innerhalb von Funktionen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="09c39-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="09c39-115">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="09c39-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09c39-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="09c39-116">Requirements</span></span>  
 <span data-ttu-id="09c39-117">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09c39-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09c39-118">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="09c39-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="09c39-119">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09c39-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09c39-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09c39-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09c39-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09c39-121">See also</span></span>

- [<span data-ttu-id="09c39-122">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="09c39-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
