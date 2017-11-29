---
title: ICorDebugFunctionBreakpoint Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunctionBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunctionBreakpoint
helpviewer_keywords: ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: 9c149303-14b1-4138-83d7-e8c3e0fcd332
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 910317bea8af3a80ee66544651de2372808734bb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunctionbreakpoint-interface1"></a><span data-ttu-id="96402-102">ICorDebugFunctionBreakpoint Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="96402-102">ICorDebugFunctionBreakpoint Interface1</span></span>
<span data-ttu-id="96402-103">Erweitert die ICorDebugBreakpoint-Schnittstelle, um Haltepunkte innerhalb von Funktionen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="96402-103">Extends the ICorDebugBreakpoint interface to support breakpoints within functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="96402-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="96402-104">Methods</span></span>  
  
|<span data-ttu-id="96402-105">Methode</span><span class="sxs-lookup"><span data-stu-id="96402-105">Method</span></span>|<span data-ttu-id="96402-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="96402-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="96402-107">GetFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="96402-107">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getfunction-method.md)|<span data-ttu-id="96402-108">Ruft einen Schnittstellenzeiger auf eine ICorDebugFunction ab, die die Funktion verweist, in der der Breakpoint festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="96402-108">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>|  
|[<span data-ttu-id="96402-109">GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="96402-109">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getoffset-method.md)|<span data-ttu-id="96402-110">Ruft den Offset des Haltepunkts innerhalb der Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="96402-110">Gets the offset of the breakpoint within the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96402-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="96402-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96402-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="96402-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96402-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="96402-113">Requirements</span></span>  
 <span data-ttu-id="96402-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96402-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96402-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="96402-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96402-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96402-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96402-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96402-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96402-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96402-118">See Also</span></span>  
 [<span data-ttu-id="96402-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="96402-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
