---
title: ICorDebugStackWalk-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk
helpviewer_keywords:
- ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 16d695e8-975d-431b-8421-e9e6c3e3f476
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06ce2da435df9458ca59d76fa426becbede2e619
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959672"
---
# <a name="icordebugstackwalk-interface"></a><span data-ttu-id="f3850-102">ICorDebugStackWalk-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f3850-102">ICorDebugStackWalk Interface</span></span>
<span data-ttu-id="f3850-103">Stellt Methoden zum Abrufen der verwalteten Methoden oder Frames auf dem Stapel eines Threads bereit.</span><span class="sxs-lookup"><span data-stu-id="f3850-103">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f3850-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="f3850-104">Methods</span></span>  
  
|<span data-ttu-id="f3850-105">Methode</span><span class="sxs-lookup"><span data-stu-id="f3850-105">Method</span></span>|<span data-ttu-id="f3850-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f3850-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f3850-107">GetContext-Methode</span><span class="sxs-lookup"><span data-stu-id="f3850-107">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)|<span data-ttu-id="f3850-108">Gibt den Kontext für den aktuellen Frame im `ICorDebugStackWalk` -Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="f3850-108">Returns the context for the current frame in the `ICorDebugStackWalk` object.</span></span>|  
|[<span data-ttu-id="f3850-109">SetContext-Methode</span><span class="sxs-lookup"><span data-stu-id="f3850-109">SetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md)|<span data-ttu-id="f3850-110">Legt den `ICorDebugStackWalk` aktuellen Kontext des Objekts auf einen gültigen Kontext für den Thread fest.</span><span class="sxs-lookup"><span data-stu-id="f3850-110">Sets the `ICorDebugStackWalk` object’s current context to a valid context for the thread.</span></span>|  
|[<span data-ttu-id="f3850-111">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="f3850-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)|<span data-ttu-id="f3850-112">Verschiebt das `ICorDebugStackWalk` -Objekt in den nächsten Frame.</span><span class="sxs-lookup"><span data-stu-id="f3850-112">Moves the `ICorDebugStackWalk` object to the next frame.</span></span>|  
|[<span data-ttu-id="f3850-113">GetFrame-Methode</span><span class="sxs-lookup"><span data-stu-id="f3850-113">GetFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getframe-method.md)|<span data-ttu-id="f3850-114">Ruft den aktuellen Frame im `ICorDebugStackWalk` -Objekt ab.</span><span class="sxs-lookup"><span data-stu-id="f3850-114">Gets the current frame in the `ICorDebugStackWalk` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3850-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f3850-115">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f3850-116">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f3850-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3850-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f3850-117">Requirements</span></span>  
 <span data-ttu-id="f3850-118">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3850-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3850-119">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="f3850-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3850-120">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3850-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3850-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3850-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3850-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3850-122">See also</span></span>

- [<span data-ttu-id="f3850-123">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f3850-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f3850-124">Debuggen</span><span class="sxs-lookup"><span data-stu-id="f3850-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
