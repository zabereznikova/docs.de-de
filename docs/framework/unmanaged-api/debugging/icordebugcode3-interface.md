---
title: ICorDebugCode3-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugCode3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode3
helpviewer_keywords:
- ICorDebugCode3 interface [.NET Framework debugging]
ms.assetid: 70f07c9e-0614-4bee-ac34-09fe6c51c5a9
topic_type:
- apiref
ms.openlocfilehash: 609cd557db71fac53aadf613534a23e988b14bde
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720756"
---
# <a name="icordebugcode3-interface"></a><span data-ttu-id="fdb9d-102">ICorDebugCode3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fdb9d-102">ICorDebugCode3 Interface</span></span>

<span data-ttu-id="fdb9d-103">Stellt eine Methode bereit, die "ICorDebugCode" und "ICorDebugCode2" erweitert, um Informationen über einen verwalteten Rückgabewert bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="fdb9d-103">Provides a method that extends "ICorDebugCode" and "ICorDebugCode2" to provide information about a managed return value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fdb9d-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="fdb9d-104">Methods</span></span>  
  
|<span data-ttu-id="fdb9d-105">Methode</span><span class="sxs-lookup"><span data-stu-id="fdb9d-105">Method</span></span>|<span data-ttu-id="fdb9d-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fdb9d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fdb9d-107">GetReturnValueLiveOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="fdb9d-107">GetReturnValueLiveOffset Method</span></span>](icordebugcode3-getreturnvalueliveoffset-method.md)|<span data-ttu-id="fdb9d-108">Ruft während eines festgelegten IL-Offsets die systemeigenen Offsets ab, in denen ein Haltepunkt eingefügt werden sollte, damit der Debugger den Rückgabewert aus einer Funktion abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="fdb9d-108">For a specified IL offset, gets the native offsets where a breakpoint should be placed so that the debugger can obtain the return value from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fdb9d-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fdb9d-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fdb9d-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="fdb9d-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdb9d-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fdb9d-111">Requirements</span></span>  

 <span data-ttu-id="fdb9d-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fdb9d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdb9d-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fdb9d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fdb9d-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fdb9d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fdb9d-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdb9d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdb9d-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fdb9d-116">See also</span></span>

- [<span data-ttu-id="fdb9d-117">ICorDebugILFrame3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fdb9d-117">ICorDebugILFrame3 Interface</span></span>](icordebugilframe3-interface.md)
- [<span data-ttu-id="fdb9d-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="fdb9d-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
