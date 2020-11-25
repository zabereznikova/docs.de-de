---
title: ICorDebugFunctionBreakpoint-Schnittstelle
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
ms.openlocfilehash: 0f1e6bbdf16c953b0dd22d9dfa44bc3585f1269e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726248"
---
# <a name="icordebugfunctionbreakpoint-interface"></a><span data-ttu-id="b826f-102">ICorDebugFunctionBreakpoint-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b826f-102">ICorDebugFunctionBreakpoint Interface</span></span>

<span data-ttu-id="b826f-103">Erweitert die ICorDebugBreakpoint-Schnittstelle, um Breakpoints innerhalb von Funktionen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="b826f-103">Extends the ICorDebugBreakpoint interface to support breakpoints within functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b826f-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="b826f-104">Methods</span></span>  
  
|<span data-ttu-id="b826f-105">Methode</span><span class="sxs-lookup"><span data-stu-id="b826f-105">Method</span></span>|<span data-ttu-id="b826f-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b826f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b826f-107">GetFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="b826f-107">GetFunction Method</span></span>](icordebugfunctionbreakpoint-getfunction-method.md)|<span data-ttu-id="b826f-108">Ruft einen Schnittstellen Zeiger auf eine icordebufunction ab, die auf die Funktion verweist, in der der Breakpoint festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b826f-108">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>|  
|[<span data-ttu-id="b826f-109">GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="b826f-109">GetOffset Method</span></span>](icordebugfunctionbreakpoint-getoffset-method.md)|<span data-ttu-id="b826f-110">Ruft den Offset des Breakpoints innerhalb der Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="b826f-110">Gets the offset of the breakpoint within the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b826f-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b826f-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b826f-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b826f-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b826f-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b826f-113">Requirements</span></span>  

 <span data-ttu-id="b826f-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b826f-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b826f-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b826f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b826f-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b826f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b826f-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b826f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b826f-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b826f-118">See also</span></span>

- [<span data-ttu-id="b826f-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="b826f-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
