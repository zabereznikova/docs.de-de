---
title: ICorDebugFunctionBreakpoint Schnittstelle1
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6cd4c430798333dd22c36ce30e7c9ce05bdc8f56
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414182"
---
# <a name="icordebugfunctionbreakpoint-interface1"></a><span data-ttu-id="22b4a-102">ICorDebugFunctionBreakpoint Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="22b4a-102">ICorDebugFunctionBreakpoint Interface1</span></span>
<span data-ttu-id="22b4a-103">Erweitert die ICorDebugBreakpoint-Schnittstelle, um Haltepunkte innerhalb von Funktionen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="22b4a-103">Extends the ICorDebugBreakpoint interface to support breakpoints within functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="22b4a-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="22b4a-104">Methods</span></span>  
  
|<span data-ttu-id="22b4a-105">Methode</span><span class="sxs-lookup"><span data-stu-id="22b4a-105">Method</span></span>|<span data-ttu-id="22b4a-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="22b4a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="22b4a-107">GetFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="22b4a-107">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getfunction-method.md)|<span data-ttu-id="22b4a-108">Ruft einen Schnittstellenzeiger auf eine ICorDebugFunction ab, die die Funktion verweist, in der der Breakpoint festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="22b4a-108">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>|  
|[<span data-ttu-id="22b4a-109">GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="22b4a-109">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getoffset-method.md)|<span data-ttu-id="22b4a-110">Ruft den Offset des Haltepunkts innerhalb der Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="22b4a-110">Gets the offset of the breakpoint within the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22b4a-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="22b4a-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="22b4a-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="22b4a-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22b4a-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="22b4a-113">Requirements</span></span>  
 <span data-ttu-id="22b4a-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22b4a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22b4a-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22b4a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22b4a-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22b4a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22b4a-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22b4a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22b4a-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22b4a-118">See Also</span></span>  
 [<span data-ttu-id="22b4a-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="22b4a-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
