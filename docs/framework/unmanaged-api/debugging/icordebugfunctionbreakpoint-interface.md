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
ms.openlocfilehash: 5e3804335bacefad61c4f521ea1ef1444b7b1fed
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777704"
---
# <a name="icordebugfunctionbreakpoint-interface"></a><span data-ttu-id="daeca-102">ICorDebugFunctionBreakpoint-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="daeca-102">ICorDebugFunctionBreakpoint Interface</span></span>

<span data-ttu-id="daeca-103">Erweitert die ICorDebugBreakpoint-Schnittstelle, um Breakpoints innerhalb von Funktionen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="daeca-103">Extends the ICorDebugBreakpoint interface to support breakpoints within functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="daeca-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="daeca-104">Methods</span></span>  
  
|<span data-ttu-id="daeca-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="daeca-105">Method</span></span>|<span data-ttu-id="daeca-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="daeca-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="daeca-107">GetFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="daeca-107">GetFunction Method</span></span>](icordebugfunctionbreakpoint-getfunction-method.md)|<span data-ttu-id="daeca-108">Ruft einen Schnittstellen Zeiger auf eine icordebufunction ab, die auf die Funktion verweist, in der der Breakpoint festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="daeca-108">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>|  
|[<span data-ttu-id="daeca-109">GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="daeca-109">GetOffset Method</span></span>](icordebugfunctionbreakpoint-getoffset-method.md)|<span data-ttu-id="daeca-110">Ruft den Offset des Breakpoints innerhalb der Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="daeca-110">Gets the offset of the breakpoint within the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="daeca-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="daeca-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="daeca-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="daeca-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="daeca-113">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="daeca-113">Requirements</span></span>  
 <span data-ttu-id="daeca-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="daeca-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="daeca-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="daeca-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="daeca-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="daeca-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="daeca-117">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="daeca-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daeca-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="daeca-118">See also</span></span>

- [<span data-ttu-id="daeca-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="daeca-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
