---
title: ICorDebugStackWalk-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStackWalk
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStackWalk
helpviewer_keywords: ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 16d695e8-975d-431b-8421-e9e6c3e3f476
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0c8a4421b716614081368755388bd2ab8d8fe22e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugstackwalk-interface"></a><span data-ttu-id="44959-102">ICorDebugStackWalk-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="44959-102">ICorDebugStackWalk Interface</span></span>
<span data-ttu-id="44959-103">Stellt Methoden zum Abrufen der verwalteten Methoden oder Frames auf dem Stapel eines Threads bereit.</span><span class="sxs-lookup"><span data-stu-id="44959-103">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="44959-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="44959-104">Methods</span></span>  
  
|<span data-ttu-id="44959-105">Methode</span><span class="sxs-lookup"><span data-stu-id="44959-105">Method</span></span>|<span data-ttu-id="44959-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="44959-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="44959-107">GetContext-Methode</span><span class="sxs-lookup"><span data-stu-id="44959-107">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)|<span data-ttu-id="44959-108">Gibt den Kontext für den aktuellen Frame in der `ICorDebugStackWalk` Objekt.</span><span class="sxs-lookup"><span data-stu-id="44959-108">Returns the context for the current frame in the `ICorDebugStackWalk` object.</span></span>|  
|[<span data-ttu-id="44959-109">SetContext-Methode</span><span class="sxs-lookup"><span data-stu-id="44959-109">SetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md)|<span data-ttu-id="44959-110">Legt die `ICorDebugStackWalk` aktuellen Kontext des Objekts, um einen gültigen Kontext für den Thread.</span><span class="sxs-lookup"><span data-stu-id="44959-110">Sets the `ICorDebugStackWalk` object’s current context to a valid context for the thread.</span></span>|  
|[<span data-ttu-id="44959-111">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="44959-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)|<span data-ttu-id="44959-112">Verschiebt die `ICorDebugStackWalk` Objekt, das den nächsten Frame.</span><span class="sxs-lookup"><span data-stu-id="44959-112">Moves the `ICorDebugStackWalk` object to the next frame.</span></span>|  
|[<span data-ttu-id="44959-113">GetFrame-Methode</span><span class="sxs-lookup"><span data-stu-id="44959-113">GetFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getframe-method.md)|<span data-ttu-id="44959-114">Ruft den aktuellen Frame in der `ICorDebugStackWalk` Objekt.</span><span class="sxs-lookup"><span data-stu-id="44959-114">Gets the current frame in the `ICorDebugStackWalk` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44959-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="44959-115">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="44959-116">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="44959-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44959-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="44959-117">Requirements</span></span>  
 <span data-ttu-id="44959-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44959-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44959-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44959-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44959-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44959-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44959-121">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44959-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44959-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44959-122">See Also</span></span>  
 [<span data-ttu-id="44959-123">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="44959-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="44959-124">Debuggen</span><span class="sxs-lookup"><span data-stu-id="44959-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
