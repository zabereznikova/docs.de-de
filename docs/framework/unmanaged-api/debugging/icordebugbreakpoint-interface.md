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
ms.openlocfilehash: a68e061c6def61746ee65f8a25818f8dbcd785b5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59159730"
---
# <a name="icordebugbreakpoint-interface"></a><span data-ttu-id="a4118-102">ICorDebugBreakpoint-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a4118-102">ICorDebugBreakpoint Interface</span></span>

<span data-ttu-id="a4118-103">Stellt einen Haltepunkt in einer Funktion oder einen Beobachtungspunkt für einen Wert dar.</span><span class="sxs-lookup"><span data-stu-id="a4118-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a4118-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="a4118-104">Methods</span></span>  
  
|<span data-ttu-id="a4118-105">Methode</span><span class="sxs-lookup"><span data-stu-id="a4118-105">Method</span></span>|<span data-ttu-id="a4118-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4118-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a4118-107">Activate-Methode</span><span class="sxs-lookup"><span data-stu-id="a4118-107">Activate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|<span data-ttu-id="a4118-108">Legt den aktiven Zustand dieses `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="a4118-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="a4118-109">IsActive-Methode</span><span class="sxs-lookup"><span data-stu-id="a4118-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="a4118-110">Ruft einen Wert, der angibt, ob dies `ICorDebugBreakpoint` aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="a4118-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4118-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a4118-111">Remarks</span></span>  
 <span data-ttu-id="a4118-112">Haltepunkte unterstützen die bedingte Ausdrücke nicht direkt.</span><span class="sxs-lookup"><span data-stu-id="a4118-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="a4118-113">Wenn eine solche Funktionalität gewünscht ist, muss ein Debugger implementieren oberhalb des `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="a4118-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="a4118-114">ICorDebugFunctionBreakpoint-Schnittstelle erweitert `ICorDebugBreakpoint` um Haltepunkte innerhalb von Funktionen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a4118-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4118-115">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a4118-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4118-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a4118-116">Requirements</span></span>  
 <span data-ttu-id="a4118-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4118-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4118-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a4118-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4118-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4118-119">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a4118-120">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="a4118-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a4118-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a4118-121">See also</span></span>

- [<span data-ttu-id="a4118-122">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="a4118-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
