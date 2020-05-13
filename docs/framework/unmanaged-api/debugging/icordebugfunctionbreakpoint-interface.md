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
ms.openlocfilehash: 6a378e3579ab9ea8d9534a408d0e456373616cad
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213139"
---
# <a name="icordebugfunctionbreakpoint-interface"></a><span data-ttu-id="f4419-102">ICorDebugFunctionBreakpoint-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f4419-102">ICorDebugFunctionBreakpoint Interface</span></span>

<span data-ttu-id="f4419-103">Erweitert die ICorDebugBreakpoint-Schnittstelle, um Breakpoints innerhalb von Funktionen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="f4419-103">Extends the ICorDebugBreakpoint interface to support breakpoints within functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f4419-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="f4419-104">Methods</span></span>  
  
|<span data-ttu-id="f4419-105">Methode</span><span class="sxs-lookup"><span data-stu-id="f4419-105">Method</span></span>|<span data-ttu-id="f4419-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f4419-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f4419-107">GetFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="f4419-107">GetFunction Method</span></span>](icordebugfunctionbreakpoint-getfunction-method.md)|<span data-ttu-id="f4419-108">Ruft einen Schnittstellen Zeiger auf eine icordebufunction ab, die auf die Funktion verweist, in der der Breakpoint festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f4419-108">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>|  
|[<span data-ttu-id="f4419-109">GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="f4419-109">GetOffset Method</span></span>](icordebugfunctionbreakpoint-getoffset-method.md)|<span data-ttu-id="f4419-110">Ruft den Offset des Breakpoints innerhalb der Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="f4419-110">Gets the offset of the breakpoint within the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4419-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f4419-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f4419-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f4419-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4419-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f4419-113">Requirements</span></span>  
 <span data-ttu-id="f4419-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4419-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4419-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f4419-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f4419-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4419-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4419-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4419-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4419-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4419-118">See also</span></span>

- [<span data-ttu-id="f4419-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f4419-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
