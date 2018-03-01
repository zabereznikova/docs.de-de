---
title: ICorDebugFunctionBreakpoint Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugFunctionBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint
helpviewer_keywords:
- ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: 9c149303-14b1-4138-83d7-e8c3e0fcd332
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 019a94243773fcb1751f419d8e38a6759fa1d3bd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunctionbreakpoint-interface1"></a><span data-ttu-id="b8d6c-102">ICorDebugFunctionBreakpoint Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="b8d6c-102">ICorDebugFunctionBreakpoint Interface1</span></span>
<span data-ttu-id="b8d6c-103">Erweitert die ICorDebugBreakpoint-Schnittstelle, um Haltepunkte innerhalb von Funktionen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="b8d6c-103">Extends the ICorDebugBreakpoint interface to support breakpoints within functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b8d6c-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="b8d6c-104">Methods</span></span>  
  
|<span data-ttu-id="b8d6c-105">Methode</span><span class="sxs-lookup"><span data-stu-id="b8d6c-105">Method</span></span>|<span data-ttu-id="b8d6c-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b8d6c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b8d6c-107">GetFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="b8d6c-107">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getfunction-method.md)|<span data-ttu-id="b8d6c-108">Ruft einen Schnittstellenzeiger auf eine ICorDebugFunction ab, die die Funktion verweist, in der der Breakpoint festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="b8d6c-108">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>|  
|[<span data-ttu-id="b8d6c-109">GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="b8d6c-109">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getoffset-method.md)|<span data-ttu-id="b8d6c-110">Ruft den Offset des Haltepunkts innerhalb der Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="b8d6c-110">Gets the offset of the breakpoint within the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8d6c-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b8d6c-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8d6c-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b8d6c-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8d6c-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b8d6c-113">Requirements</span></span>  
 <span data-ttu-id="b8d6c-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8d6c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8d6c-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b8d6c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b8d6c-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8d6c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8d6c-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8d6c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8d6c-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8d6c-118">See Also</span></span>  
 [<span data-ttu-id="b8d6c-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b8d6c-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
