---
title: ICorDebugFunctionBreakpoint-Schnittstelle1
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
ms.openlocfilehash: b8403873fb7bc15e3109821bf738d7b68e20f878
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662685"
---
# <a name="icordebugfunctionbreakpoint-interface1"></a><span data-ttu-id="397f4-102">ICorDebugFunctionBreakpoint-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="397f4-102">ICorDebugFunctionBreakpoint Interface1</span></span>
<span data-ttu-id="397f4-103">Erweitert die ICorDebugBreakpoint-Schnittstelle, um Haltepunkte innerhalb von Funktionen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="397f4-103">Extends the ICorDebugBreakpoint interface to support breakpoints within functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="397f4-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="397f4-104">Methods</span></span>  
  
|<span data-ttu-id="397f4-105">Methode</span><span class="sxs-lookup"><span data-stu-id="397f4-105">Method</span></span>|<span data-ttu-id="397f4-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="397f4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="397f4-107">GetFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="397f4-107">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getfunction-method.md)|<span data-ttu-id="397f4-108">Ruft einen Schnittstellenzeiger auf eine ICorDebugFunction ab, die die Funktion verweist, in der der Haltepunkt gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="397f4-108">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>|  
|[<span data-ttu-id="397f4-109">GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="397f4-109">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getoffset-method.md)|<span data-ttu-id="397f4-110">Ruft den Offset des Haltepunkts in der Funktion.</span><span class="sxs-lookup"><span data-stu-id="397f4-110">Gets the offset of the breakpoint within the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="397f4-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="397f4-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="397f4-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="397f4-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="397f4-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="397f4-113">Requirements</span></span>  
 <span data-ttu-id="397f4-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="397f4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="397f4-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="397f4-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="397f4-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="397f4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="397f4-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="397f4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="397f4-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="397f4-118">See also</span></span>
- [<span data-ttu-id="397f4-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="397f4-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
