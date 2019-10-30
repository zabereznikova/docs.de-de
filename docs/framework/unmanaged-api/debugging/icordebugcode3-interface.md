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
ms.openlocfilehash: f3ae25f7d16600a1b09f30f96a191d7ecf76713e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121067"
---
# <a name="icordebugcode3-interface"></a><span data-ttu-id="f43f8-102">ICorDebugCode3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f43f8-102">ICorDebugCode3 Interface</span></span>
<span data-ttu-id="f43f8-103">Stellt eine Methode bereit, die "ICorDebugCode" und "ICorDebugCode2" erweitert, um Informationen über einen verwalteten Rückgabewert bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="f43f8-103">Provides a method that extends "ICorDebugCode" and "ICorDebugCode2" to provide information about a managed return value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f43f8-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="f43f8-104">Methods</span></span>  
  
|<span data-ttu-id="f43f8-105">Methode</span><span class="sxs-lookup"><span data-stu-id="f43f8-105">Method</span></span>|<span data-ttu-id="f43f8-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f43f8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f43f8-107">GetReturnValueLiveOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="f43f8-107">GetReturnValueLiveOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)|<span data-ttu-id="f43f8-108">Ruft während eines festgelegten IL-Offsets die systemeigenen Offsets ab, in denen ein Haltepunkt eingefügt werden sollte, damit der Debugger den Rückgabewert aus einer Funktion abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="f43f8-108">For a specified IL offset, gets the native offsets where a breakpoint should be placed so that the debugger can obtain the return value from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f43f8-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f43f8-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f43f8-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f43f8-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f43f8-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f43f8-111">Requirements</span></span>  
 <span data-ttu-id="f43f8-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f43f8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f43f8-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f43f8-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f43f8-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f43f8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f43f8-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f43f8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f43f8-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f43f8-116">See also</span></span>

- [<span data-ttu-id="f43f8-117">ICorDebugILFrame3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f43f8-117">ICorDebugILFrame3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)
- [<span data-ttu-id="f43f8-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f43f8-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
