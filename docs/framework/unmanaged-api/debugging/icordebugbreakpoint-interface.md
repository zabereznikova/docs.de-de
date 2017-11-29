---
title: ICorDebugBreakpoint Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugBreakpoint
helpviewer_keywords: ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: aa5ad3d7-e1bb-42af-99bc-471224e3bcaa
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b78b61b99fb8f236e787f3acbf993d0a1c57e797
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugbreakpoint-interface1"></a><span data-ttu-id="86610-102">ICorDebugBreakpoint Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="86610-102">ICorDebugBreakpoint Interface1</span></span>
<span data-ttu-id="86610-103">Stellt einen Haltepunkt in einer Funktion oder einen Beobachtungspunkt für einen Wert dar.</span><span class="sxs-lookup"><span data-stu-id="86610-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="86610-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="86610-104">Methods</span></span>  
  
|<span data-ttu-id="86610-105">Methode</span><span class="sxs-lookup"><span data-stu-id="86610-105">Method</span></span>|<span data-ttu-id="86610-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="86610-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="86610-107">Activate-Methode</span><span class="sxs-lookup"><span data-stu-id="86610-107">Activate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|<span data-ttu-id="86610-108">Legt den Zustand "aktiven" dieses `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="86610-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="86610-109">IsActive-Methode</span><span class="sxs-lookup"><span data-stu-id="86610-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="86610-110">Ruft einen Wert, der angibt, ob dies `ICorDebugBreakpoint` aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="86610-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86610-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="86610-111">Remarks</span></span>  
 <span data-ttu-id="86610-112">Bedingte Ausdrücke unterstützt Haltepunkte nicht direkt.</span><span class="sxs-lookup"><span data-stu-id="86610-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="86610-113">Wenn solche Funktionen gewünscht ist, muss ein Debugger implementieren sie auf der Basis von `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="86610-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="86610-114">ICorDebugFunctionBreakpoint-Schnittstelle erweitert `ICorDebugBreakpoint` um Haltepunkte innerhalb von Funktionen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="86610-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="86610-115">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="86610-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86610-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="86610-116">Requirements</span></span>  
 <span data-ttu-id="86610-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86610-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86610-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="86610-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="86610-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86610-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86610-120">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86610-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86610-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86610-121">See Also</span></span>  
 [<span data-ttu-id="86610-122">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="86610-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
