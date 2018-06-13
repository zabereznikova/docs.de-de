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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: febfe7df52a0c1f44cb156faf2da310d317e01a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411324"
---
# <a name="icordebugcode3-interface"></a><span data-ttu-id="16c86-102">ICorDebugCode3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="16c86-102">ICorDebugCode3 Interface</span></span>
<span data-ttu-id="16c86-103">Stellt eine Methode, die erweitert "ICorDebugCode" und "ICorDebugCode2", um Informationen zu einem verwalteten Rückgabewert bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="16c86-103">Provides a method that extends "ICorDebugCode" and "ICorDebugCode2" to provide information about a managed return value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="16c86-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="16c86-104">Methods</span></span>  
  
|<span data-ttu-id="16c86-105">Methode</span><span class="sxs-lookup"><span data-stu-id="16c86-105">Method</span></span>|<span data-ttu-id="16c86-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="16c86-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="16c86-107">GetReturnValueLiveOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="16c86-107">GetReturnValueLiveOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)|<span data-ttu-id="16c86-108">Ruft während eines festgelegten IL-Offsets die systemeigenen Offsets ab, in denen ein Haltepunkt eingefügt werden sollte, damit der Debugger den Rückgabewert aus einer Funktion abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="16c86-108">For a specified IL offset, gets the native offsets where a breakpoint should be placed so that the debugger can obtain the return value from a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16c86-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="16c86-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="16c86-110">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="16c86-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16c86-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="16c86-111">Requirements</span></span>  
 <span data-ttu-id="16c86-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16c86-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16c86-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="16c86-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="16c86-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16c86-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16c86-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16c86-115">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16c86-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16c86-116">See Also</span></span>  
    
    
    
 [<span data-ttu-id="16c86-117">ICorDebugILFrame3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="16c86-117">ICorDebugILFrame3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)  
 [<span data-ttu-id="16c86-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="16c86-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
